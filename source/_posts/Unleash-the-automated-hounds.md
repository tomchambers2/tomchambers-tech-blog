title: Unleash the automated hounds
date: 2015-11-19 16:08:07
tags:
---
The dream of watching a world change its shape according to one’s desires without having to make the barest of efforts. This is what leads a programmer to spend an entire weekend of perfect weather inside a dark stuffy room making a lamp turn on and off when he says ‘lights on’. So I find myself here with as complete a setup as I’ll probably ever have I thought I might share it with the wider world (since no-one else is ever coming up here).

Since I live in London, I rent a room so small I repeatedly hit my head on the ceiling when I try to get to my wardrobe. I’m also limited in what I can tear out of the walls and change. So my setup is based around lights, sound and controllers. I’ve got two wemo motion sensors, two switches which control two extension leads with two and three lamps respectively and an LIFX bulb in a lamp. I’ve got a raspberry pi which has a USB microphone and a set of powered speakers as well as a Leap Motion controller. The raspberry pi also runs most of the services required and the MQTT message broker.

My brief thoughts on the quality of these products:

- LIFX: brilliant setup, has a great HTTP API as well as the LAN communication I’m using (with the excellent python bindings by mclarkk). Rather expensive at £60 though, and the colour changing is of limited use really.
- WEMO: devices themselves are good. They use a relay which makes a loud click when turning on and off. The app is horrendous and makes setup a chore. Switches are now £30 which isn’t too bad but not really at average consumer level yet
- Leap Motion: impractical for everyday computer use. But as a single controller it seems to work well. Mine was £27.50 on ebay and some are going for as low as £18, so pretty well priced. Hard to integrate into this system without a fair of custom software though.

## Architectural thoughts
The whole thing is built with a microservices architecture - each function, whether it be input or output, is running as its own separate service. I toyed with the idea of making the services use HTTP as it seemed simpler and the overheads didn’t really matter for such low volume. I wanted to experiment with messaging however and I’m glad I did as it made the whole process much easier and the system is now far more flexible. The mosquitto broker is very simple to setup and works on the pi and there are equally simple clients for python, node and whatever else. Connecting is as simple as this (Python):

client = mqtt.Client("lifx_controller")
client.on_connect = on_connect
client.message_callback_add('lights/on', turn_lights_on)

And now you’re listening to events. Each service is dumb to whatever other services do. They’re basically a bunch of idiots running around shouting, “it’s dark now, turn the lights on!” or “somebody moved!” without any concern for who’s picking it up. Which makes it easy to develop those things in isolation and build functionality for future services.

One thing that bothers me is that there’s a complete dependency on the broker. If that goes down then absolutely nothing will happen because there’s no communication at all. Although it’s just a simple message carrier it’s what makes the loose coupling possible. I’m not sure what the solution would be here - HTTP fallbacks where services talk to each other directly would be too difficult to maintain since they would only be used in very rare failure cases. One could simply broadcast packets across the network but this doesn’t seem at all sensible and doesn’t really scale.

I had intended to use Docker to make it easy to transfer projects across and build/start them automatically on git push, but this didn’t turn out to be as useful as I’d hoped. For one, the pi’s ARM architecture prevents me from using the same Dockerfile on my macbook, so projects can only be built once they get there, so there’s no advantage of using the same environment everywhere. Builds also take a horrendously long time on the pi, possibly because it’s I/O bound to the speed of transfer to the cheap SD card.

I also considered a continuous integration solution, which would make it easier to keep the services (about 8 so far) up to date without having to SSH in and manually pull/restart the process. Using something hosted would mean exposing my pi to the internet though, which didn’t seem like a good idea since although nobody could do too much, it would let people do weird things with my lights in the middle of the night. Setting up something locally seemed a bit overkill as well.

## List of services:

- docker-mosquitto - a docker container that boots up a raspbian version of Mosquitto - an MQTT broker
- lifx-controller - python
- wemo-controller - python
- voice-controller - python, sends audio to wit.ai and outputs command messages
- leap-motion-controller
- spotify-controller - python, listens to music/playlist events and puts on a random song from that search
- moodbot - node, connects to Harmony mood api and changes lighting and music
- sun-manager - node, checks current sunlight and listens to motion events, issues lighting commands
- app-status - a dashboard in node/javascript, just listens to events. In the future it might send control events as well

## The meat of the business
By far the coolest part of the setup is the Leap Motion controller. It’s not really very useful as a general input device, but for this case where there’s only two axes it’s great. Left and right controls the colour, and up and down is power.

Next up is voice control. voice-controller is constantly listening and sends blocks of speech to wit.ai, where it gets processed into intents (lights) and entities (on or off) and then it sends a message based on that command which is picked up by the wemo-controller and lifx-controller services which communicate via LAN. The voice controller can also send messages to spotify-controller.

I used the API of an app I built (Harmony mood tracker) to tie my mood to the colour of the LIFX bulb with moodbot. It makes use of Firebase’s event driven data stream to get updates immediately rather than polling. Every time I enter a new mood it updates the colour of the bulb (but doesn’t turn it on) and updates the chosen playlist. When wemo detects motion, the lamp turns on using that colour and moodbot plays the playlist (given that it’s a reasonable time for music).

I’m intending to add a facial expression reading chrome extension to Harmony, which will allow data to be automatically collected. The system will then be giving me a subtle cue about my mood, bringing it to my attention without requiring active thought.

This is the real value of the internet of things - the manifestation of data. Here you take something intangible, like emotion, and represent it in the world with physical elements. It becomes a real part of the environment and now one can interact with that data layer in a physical human way rather than the artificial terminal-based manner we’ve become used to over the last 30 years.

So that’s it so far. The next element will likely be a doorbell, which will either be a dedicated device or an arduino listening to RF signals from the button which then feeds into the system. The great thing about this architecture is that the addition of any new element barely requires any modification to the system. The doorbot service can simply connect to the broker and send light or sound messages. It can also send a generic doorbell/active message which could then be picked up on by other future services.

I also built a dashboard which just picks up on messages and lets me keep tabs on what’s going on:

![](/images/hugo-dashboard.png)

It’s mostly for debugging, but it could be expanded into a controller in it’s own right. It’s called Hugo after Hugo Cabret the automaton. Looking at this it’s not clear to me where the business logic should go - for example the moodbot sends commands to play music when there’s motion, and the sun-manager turns lights on and off when there’s motion. These could simply be notifiers of ‘mood’ and ‘light/dark’ events with a separate action-manager service that wraps all configuration into one place.

Automation is clearly the future, and it’s on the verge of becoming cheap enough that it will soon be integrated into every household device. This system is clearly outside of the scope of most people’s skills and interest, but it certainly seems like a useful architectural pattern for connecting services together. IFTTT provides a pretty useful broker service and it might be that we see a more advanced version of that start to take responsibility for the bulk of configuration.

It does still concern me that there is a single pinch point for failure and control by a malicious actor - an alternative might be to have a configuration service which is the single point of user interaction with the system, which then distributes relevant mapping to devices so they know how to act based on what input. I think a proper solution to this problem would probably involve taking a step back and rethinking what one is trying to achieve.

There are quite a lot of pain points currently with IoT devices - a major one for me is attaching devices to wifi. I have about 10 headless devices at the moment, each one insists on my downloading an app and typing in my complex wifi password. They also each have their own quirky API to work with, there’s no standard for communication between them, hence my writing wrappers for most of them.

If there’s any details you’re interested in please email me at tom.chambers@gmail.com