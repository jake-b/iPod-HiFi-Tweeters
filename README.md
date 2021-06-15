# iPod-HiFi-Tweeters

I've developed a minor obsession with the iPod Hi-Fi.  I have become specifically obsessed with an [iPod Hi-Fi posted to reddit that has two additional tweeters](https://www.reddit.com/r/iPodHiFi/comments/mc8l05/i_bought_this_used_ipod_hifi_today_and_i_realised/).  

I decided to attempt this modification myself using a slightly abused iPod Hi-Fi I was able to aquire.

![Assembled Mod](../assets/assembled.png?raw=true)
![Exposed internals](../assets/exposed.png?raw=true)

# About the audio engineering

I'm a novice when it comes to Hi-Fi systems, amplifiers, and crossovers.  I have done my best to engineer what I think "sounds about right" and choose parts that make sense... but if you are a Hi-Fi expert and have any suggestions for how to improve this, please open an issue in GitHub, I'd love to learn more.

I have measured the mid-range speakers on the iPod Hi-Fi to be 8-ohms.  I am using 4-Ohm tweeters with a makeshift crossover consisting of an inductor and a capacitor.  I'm sure this results in a drop in overall impedence of the system,  but it does seem to work.

I can't speak to wheter the sound output is balanced across the whole frequency range, but it sounds good to my terrible ears with high frequency loss.

# What do you need

- A 3D scanner to locate the best place to cut the holes.  The baffle housing is a complex shape and there isn't much room for error.  Luckly I've done this for you, so you don't really need to figure this out for yourself.
- A CNC milling machine to cut the holes in the fascia and the internal speaker baffle housing.  You might be able to do this by hand with a dremel, but I don't think it would have the necessary polish.  I used a 3/8" endmill and a small file to clean up the corners.
- Two tweeters - I chose 4-Ohm 20W-20W 1" tweeters that are about 31mm in overall diameter.  The ones I used were marked 2000047001Z and are available on eBay and AliExpress.
- Crossover Components -  A 250uH inductor and a 8uF bi-polar capacitor.
- Connectors - The iPod Hi-Fi uses Molex MicroFit 3.0 connectors.  You can use your own to create the crossovers.
- Some adhesive foam padding - the iPod Hi-Fi is super well built.  Every wire is wrapped in foam padding. (This foam is breaking down with age on the one I have, and is now sticky.)  I wrapped any new wiring/components similarly to prevent vibration.

# Steps

1.  Disassemble the iPod Hi-Fi.  The hardest part is getting the fascia off without damaging it.  Take out both speakers, the LED, the IR receiver, and all the foam padding and place aside.
2.  Determine the hole locations.  I did a 3D scan with an IR-spraying 3D scanner and used this to find where I wanted to cut the hole:
![Hole location](../assets/hole_location.png?raw=true)
![Hole locations](../assets/hole_locations.png?raw=true)

2.  Mill the holes - put the front baffle housing back into the main cabinet and screw it down with all 8 screws.  Mount this in your milling machine.  Mill down to a depth of 11mm from the surface of the baffle housing.  This will cut the hole in the baffle and part of the black structural element in the main housing to make clearance for the tweeter.

3.  Clean out all the shavings.  Clean up the hole corners with a file.

4.  Carefully press fit the tweeters into the baffle housing.  Wire up the tweeters using a crossover.

5.  Test that everything works

6.  Cut the holes in the front fascia

6.	Reassemble

# Was the original one on reddit a prototype?

https://www.reddit.com/r/iPodHiFi/comments/mc8l05/i_bought_this_used_ipod_hifi_today_and_i_realised/

This was not a trivial modification.  It was a lot of work and involved tooling that most pople don't have.  I guess its possible someone did this following a similar procedure to what I have outlined here.

One thing that points to it being an Apple prototype: The front fascia is aluminum and it seems like the hole is annodized.  I intend to use a sharpie to hide the bright aluminum of the inside surface of the cutout.  If this was the work of a skilled modder, perhaps this is what they did as well?

THe one thing that points to the original reddit one being the work of a skillful modder is it does look to my eye like the facia around the tweeters is not fully stuck down to the baffle housing.

If anyone knows the story behind the original one, please post a GitHub issue to this repository and I'll update this document.