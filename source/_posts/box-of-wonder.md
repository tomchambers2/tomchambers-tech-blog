title: Box of Wonder
date: 2015-03-28 18:00:33
tags:
---
The Box of Wonder is a high tech fortune cookie. You put your head inside, the box scans you and prints out a prediction of your personality and date of death. It's better with the mystery, but for the sake of documentation, I'll bear all.

{% youtube G9IOsefTPPY %}

There are three spoken word audio tracks that are randomly played along with a set of lights timed to match the voice of the track as it takes you through the process. When you put your head through the curtains, it triggers a [PIR sensor](http://www.amazon.co.uk/dp/B007XQRKD4) connected to an Arduino Uno, which controls an (Adafruit Neopixel ring)[http://www.adafruit.com/product/1463], a [thermal printer](https://www.adafruit.com/products/597) and an (Adafruit Music Maker amped)[http://www.adafruit.com/product/1788] with a 3w 4ohm speaker. Because the printer and lights need a lot of amps, extra power is provided by a 5v 4 amp wall plug.

![](/images/box-of-wonder-1.jpg)

In fact, a better choice would have been a 7-12v adapter for the arduino, possibly transformed to 5v for the other components. Although the arduino runs on 5v internally, it actually needs more than this. Once everything was set up, it started resetting when printing due to the power consumption. Very confusing to someone who hasn't dealt in hardware before.

The box itself is made from plywood and covered in velvet. I also learned that making a sturdy simple box is a bit harder than it looks from the outside. Inside its covered with some [reflective silver plastic](http://www.amazon.co.uk/Mirror-Roll-Adhesive-Length-Horse/dp/B001RUFZ5C/). Works well, but very expensive compared to the rest of the supplies.

![](/images/box-of-wonder-2.jpg)

The horoscope prediction is assembled from a set of statements that psychologist [Bertram Forer](http://en.wikipedia.org/wiki/Forer_effect) came up with. They work by making statements that are vague enough and qualified enough to appear to describe anybody. I.e. sometimes you're open with others but sometimes you feel a bit hostile. The date of death is just a random date from now until 2115. The experience is pretty much as intended. The box itself is intriguing. I get a lot of looks when carting it from place to place, and told off by bus drivers when I leave it in the aisle.

Nobody believes it's doing any scanning, but there's a tiny part of the person that questions if it really knows something. I think this would be heightened if there were genuinely some questioning that it were really doing something - it could respond to interaction to appear intelligent, or make more of a pretence of doing some scanning.

It would have been nice to have some more 'scanning' devices inside the box to enhance the effect. Perhaps a head collar brain scanning thing, a bunch of gears moving around inside. I looked into disassembling a scanner to use the motorised light bar, but controlling it seemed fairly difficult so I didn't go down that path. In the end, all the ideas I had (eyes on stalks following you around?) were a bit too complex for the scope of this project, so I stuck with the lights and sound.