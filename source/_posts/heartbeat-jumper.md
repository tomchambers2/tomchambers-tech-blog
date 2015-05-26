title: Heartbeat jumper
date: 2015-03-28 18:31:10
tags:
---
The heartbeat jumper is a wearable device that measures your heartbeat and emits a soft glow on each beat. It's an arduino flora connected to a pulse sensor amped with a single red LED with a fabric patch sewn over the top for light diffusion.

Originally I had intended to use an electro luminescent panel. I tested the setup as a prototype, but there's a complication with the power supply. EL panels require high voltage AC power, which means you can't hook it straight up to an arduino and power it that way. You need either two separate power sources and a relay inbetween the inverter (converts DC battery voltage to AC) and panel or a transformer, still using a relay/transistor.

Because of the simplicity of using an LED, I went with that instead. It works fairly well, but the light is a bit small, and its not particularly diffuse. You can clearly see that it comes from a single point rather than being a glowing circle.

The biggest challenge in this project, aside from the issues with the abandoned EL idea, was the sewing. Not something I've done before. A straight line is fairly simple, but my circular sewing abilities leave something to be desired. I have improved a little though.

The idea behind the jumper is to find more ways of communicating. This isn't a particularly original project, here's an example as a [pendant](https://rainycatz.wordpress.com/2011/06/26/you-make-my-heart-flutter-wearable-sensing-device-heart-spark-hack/) and a [badge](https://learn.adafruit.com/heart-rate-badge/overview). There are many other implementations.

A second version might be on the cards. If I do go ahead with that, the main improvement will be the lighting (requires sourcing an IC to convert power and learning about transistors to turn the EL circuit on and off on the beat). I might also improve the detection. The current IR sensor requires the wearer to tape the detector to the skin, and if you move a lot it's not particularly accurate.