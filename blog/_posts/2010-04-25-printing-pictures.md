---
layout: blog
title: "Printing Pictures"
tags: "Photography"
---

 So today I wrote my first plug-in for the GIMP (it's really just a script but as it's written in Python it goes in the GIMP plug-ins directory).

The reason for the script is that I've found a print lab in the UK that will accept files over the internet and just print them without messing around trying to "correct" them. They give you an icm profile for their printer so that you can convert your images. They're called [ProAmImaging](http://www.proamimaging.com/). There are other places on the internet that seem to do the same but the sample prints I got from ProAm look pretty good so I'll be using them for now.

Anyway, the flip side of them not touching the images is that I need to scale and crop the images to the exact number of pixels needed for the print size I want. This gets tedious very quickly so I decided to write a script to automate things. What the script does is take an image size in inches, and a desired DPI, and uses them to scale and crop the image to the correct size in one step. It's nothing you couldn't do with the existing tools, but it halves the number of actions you need to do, and does the maths to work out exactly how many pixels to crop automatically.

I'd like to improve it so that it activates the crop tool with the correct aspect ratio so that you can select the crop manually, however it's not obvious to me whether that's even possible so I'll leave that for now.

A couple of things worth noting when writing Python scripts for the GIMP:

- If python doesn't like your script for some reason the GIMP won't tell you why, your script simply won't appear in the menus. There's probably a way around this but it never got so annoying that I had to figure it out. If you start with a known good script (there are loads at [registry.gimp.org](http://registry.gimp.org)) and test regularly it's OK.
- The GIMP/Python documentation seems to be rather sparse (<http://www.gimp.org/docs/python/index.html>) and the python object interface is quite small. However you can call all the [libgimp methods](http://developer.gimp.org/api/2.0/libgimp/) from Python using pbd.methodName().
- For debugging pdb.gimp_message("Your message here") is rather helpful.

Please note that this is the first time I've written a GIMP plug-in and almost the first time I've used Python so the take the above with the appropriate dosage of salt.

And finally the script itself - [ScaleAndCrop.py](/ScaleAndCrop.zip), I hope someone else finds it useful. 