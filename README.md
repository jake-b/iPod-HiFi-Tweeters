# iPod-HiFi-Tweeters

I've developed a minor obsession with the iPod Hi-Fi.  I have become specifically obsessed with an [iPod Hi-Fi posted to reddit that has two additional tweeters](https://www.reddit.com/r/iPodHiFi/comments/mc8l05/i_bought_this_used_ipod_hifi_today_and_i_realised/).  

I decided to attempt this modification myself using a slightly abused iPod Hi-Fi I was able to acquire.

![Assembled Mod](../assets/assembled.png?raw=true)
![Exposed internals](../assets/exposed.png?raw=true)

# About the audio engineering

I'm a novice when it comes to Hi-Fi systems, amplifiers, and crossovers.  I have done my best to engineer what I think "sounds about right" and choose parts that make sense... but if you are a Hi-Fi expert and have any suggestions for how to improve this, please open an issue in GitHub, I'd love to learn more.

I have measured the mid-range speakers on the iPod Hi-Fi to be 8-ohms.  I am using 4-Ohm tweeters with a makeshift crossover consisting of a 250uH inductor and a 8uF bi-polar capacitor.  I'm sure this results in a drop in overall impedance of the system,  but it does seem to work.

I can't speak to whether the sound output is balanced across the whole frequency range, but it sounds good to my terrible ears with high frequency loss.

# What do you need

- A 3D scanner to locate the best place to cut the holes.  The baffle housing is a complex shape and there isn't much room for error.  Luckily I've done this for you, so you don't really need to figure this out for yourself.
- A CNC milling machine to cut the holes in the fascia and the internal speaker baffle housing.  You might be able to do this by hand with a dremel, but I don't think it would have the necessary polish.  I used a 3/8" end mill and a small file to clean up the corners.
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
![Milling](../assets/milling.png?raw=true)

3.  Clean out all the shavings.  Clean up the hole corners with a file.

4.  Carefully press fit the tweeters into the baffle housing. 
![Tweeter Fit](../assets/tweeter_fit.png?raw=true)

5. Wire up the tweeters using two crossovers.
![Crossover](../assets/crossover.png?raw=true)

6.  Test that everything works

7.  Cut the holes in the front fascia

8.	Reassemble

# Was the original one on reddit a prototype?

https://www.reddit.com/r/iPodHiFi/comments/mc8l05/i_bought_this_used_ipod_hifi_today_and_i_realised/

This was not a trivial modification.  It was a lot of work and involved tooling that most people don't have.  I guess its possible someone did this following a similar procedure to what I have outlined here.

One thing that points to it being an Apple prototype: The front fascia is aluminum and it seems like the hole is anodized.  I intend to use a sharpie to hide the bright aluminum of the inside surface of the cutout.  If this was the work of a skilled modder, perhaps this is what they did as well?  Possibly the whole fascia was painted with matte black paint give an even finsih even through the newly cut holes.

One thing that points to the original reddit one being the work of a skillful modder: It does look to my eye like the fascia around the tweeters is not fully stuck down to the baffle housing.  Though I guess Apple could have made their prototype using existing parts.

If anyone knows the story behind the original one, please post a GitHub issue to this repository and I'll update this document.

# Speaker Mesh Frame

The iPod Hi-Fi that I used for this project came with a torn speaker mesh.  I tried to separate the frame my heating the glue but Apple used a LOT of glue to hold the two pieces together.  I would up just cytting off the back "T"-part of the frame completely, cleaning out the old speaker mesh cloth, and then wrapping the outer frame with double stick tape and new mesh.  Its better than having torn one, but a little hacked together.

THis is how the front mesh cover is constructed in case it comes in handy to someone:

![Speaker Mesh Frame](../assets/frame.png?raw=true)

# Homework

The iPod Hi-Fi is a nicely engineered product with great sound.  I much more opportunity for anyone wanting to take the work further.  (Probably not me, so this is an exercise for the reader)

- Internal AirPort 2 Receiver -- I did take a part a Airport Express with the thought of putting it inside.  I even made a passthrough for the power supply harness that borrows some volts from the 17v amplifier output and regulates it down to the 3.3v needed by the Airport Express.  The AE draws about 500mA.  In the end, I didn't do this for a few reasons:
	1.  Its hard to fit.  [I've seen others that have modified the internal housing to fit the board in](https://forums.macrumors.com/threads/ipod-hifi-airplay-2-self-contained-mod.2277829/).  I didn't really want to do this.
	2.  I didn't want to completely loose the audio in.  I have some ideas on this.

	Another possibility is to use a Raspberry Pi running [Shairport-Sync](https://github.com/mikebrady/shairport-sync) -- but this is not AirPlay 2 capable (yet).

	I did a little poking on the audio-in jack.  It accepts both mini-TOSLink (fiber optic) and traditional TRS audio signals.  THe audio-in port can tell that there's a mini-TOSLink cable installed by a switch contact that is broken when the connector is plugged in.   It can tell when there's a traditional wired audio connection because the sleeve has two contacts and the contacts are shorted when a plug is inserted.  This could be used to divert one audio signal internally (say, the TOSLink) and leave the external audio port for other uses-- but I couldn't find an external 1/8" jack with the right internal switches and also was deep enough to get through the existing case thickness.

	You could, also, for example, use a Raspberry Pi with a transistor or relay, and connect up to the wired audio input, then program the Pi to short the proper pins on the audio-in jack to make it think it has a cable plugged in.... and then un-short it when not in use, leaving the audio jack fully functional when not in use by the internal audio source.

- Better power solution -  [the Hi-Fi's power supply outputs 17v for the amplifier, 6v and 3.3v for other circuity](http://www.whatsinside.info/apple-ipod-hi-fi-dock/apple-ipod-hifi-dock-power-supply-label-detail/). (Not sure what it uses the 6v for).  I could imagine putting some sort of LiPo pack in the battery comparment and removing the the power supply board completely-- replacing it with a LiPo BMS and various buck/boost regulators to provide these needed voltage rails.  The AC connector is held in with screws, so a USB-C connector could be fashioned to screw into the same place.  Ideally this theoretical BMS would accept the various voltage ranges provided by USB-C PD, and charge the batteries, and also provide pass-through power.  One note, the iPod Hi-Fi's normal power supply provides LESS power when running on batteries, so a solution like this could let the Hi-Fi run on full power even on batteries.  [The supply puts out other signals too](https://github.com/newtonresearch/ipod-hifi-smps/blob/master/PA-3150%20PCB.pdf), such as SLEEP EN, Battery Good, Battery Low, etc that would have to be reverse engineered a bit.  I did a little searching, but couldn't find anything that immediately ticked all the boxes for this solution.