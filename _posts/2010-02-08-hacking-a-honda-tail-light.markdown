---
date: '2010-02-08 22:23:15'
layout: post
slug: hacking-a-honda-tail-light
status: publish
title: Hacking a Honda Tail Light
wordpress_id: '372'
categories:
- Local Project Blog
---

**_Editor's Note_**_: As part of my position as Editor at HeatSync Labs, I get to put on a reporter hat and take the spotlight of the Information Super Highway on our local Arizona makers, hackers, and tinkerers.  If you or anyone you know is building something pretty awesome and they're within driving distance, leave a comment and I'll see if I can follow up on it.  This $timeFrame's features maker is Nate Plamondon, who is creating a home brew tail light for his Honda motorcycle._

Here in the MC we're known for having some pretty bad car drivers running the streets.  Nate rides a motorcycle, so he knows this first hand.  Since cagers auto drivers are sometimes too busy discussing the latest episode of LOST on their iPhones while smacking their kids around in the backseat for spilling Cactus Cooler on the upholstery, they don't always notice the bikers they share the road with.  Nate wanted to try to fix this problem by making his tail light brighter, but The Man wanted to charge him between $60 to $300 for a conversion kit, and he thought that was “a little excessive for a flashing friggin' light.”

“This one is about $10 in parts, although that's also with $50 worth of new tools and failed prototypes.”  Nate showed me his latest prototype, the third version of a series of prototypes.  “The first one just failed, the second one used 50 LEDs and far, far too much power... and it didn't fit.”  The current model was sketched out first, and ExpressPCB (on Windows; Sadly they don't yet have a Linux client) was used to design the circuitry.

{% include JB/setup %}
{% assign caption_text = "Photo by .dh. Distributed under a Creative Commons Attribution 2.0 Generic License." %}
{% assign caption_photo = "http://www.heatsynclabs.org/wp-content/uploads/2010/02/4323967988_fdfff7358b.jpg" %}
{% assign caption_photo_url = "http://www.flickr.com/photos/25968780@N03/4323967988/in/pool-heatsynclabs" %}
{% include heatsynclabs/caption %}

This model contains 26 red LEDs for running and brake light as well as 2 white LEDs to illuminate a license plate, which is right below the tail light housing.  The three-line cable connecting it to the bike's lighting system brings two different voltage sources in; One is always on (normal running light) and the other one is applied when the brakes are hit.  The power in a bike tail light socket is made to handle a 5-watt running, 21-watt brake bulb, and since this uses LEDs, they draw a lot less power.  The combined 26 LEDs on this draw ~2 watts running and ~4 watts brake at full power with all LEDs active.

At the core of the design is an NE555p, a timer chip which will output a different square wave depending on the ratio of resistance between two of its pins.  “This is a grid board, with wires connecting large distances and solder bridges connecting connections with neighboring through-holes.”  Look closely at the back of the board: “In some parts I used the leftover leads from LEDs to bridge two points together on the back to avoid adding more wire.”  Clever hacks, people.

{% include JB/setup %}
{% assign caption_text = "Photo by .dh. Distributed under a Creative Commons Attribution-Non-Commercial 2.0 Generic License." %}
{% assign caption_photo = "http://www.heatsynclabs.org/wp-content/uploads/2010/02/4339119957_f3b1091937.jpg" %}
{% assign caption_photo_url = "http://www.flickr.com/photos/25968780@N03/4339119957/in/pool-heatsynclabs" %}
{% include heatsynclabs/caption %}

Although there isn't anything functionally broken in this version, Nate points out that there are improvements that would have to be made in the next version before putting it in his bike.  “[This prototype] would only work with a clear lens since red light cover with red LEDs equals weak pinkish light.”  Aside from using brighter white LEDs, it will also lack the 3-pin modular power connector that was used in the current version, and add some kind of mount to actually keep it in place inside the light cover.  “A printed circuit board will be ideal if I make more than one, too.”

But wait, there's more!

Back by popular demand, hardware now comes with schematics, but only for a limited time!


[![Shematic](http://www.heatsynclabs.org/wp-content/uploads/2010/02/bike3_schematic.png)](http://www.heatsynclabs.org/wp-content/uploads/2010/02/bike3_schematic.png)





IC1                        LM555




T1                          2N3906




C1                          100uF electrolytic




C2                          100nf mylar




D1,2                      1N4006




R1,10                    330 ohm




R2,3                      10k ohm




R4,6                      1k ohm




R5                         47k ohm




R7,8,9,11,12      100 ohm
