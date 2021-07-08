---
layout: blog
title: "High Pass Filter Effect"
tags: "Photography"
---

This technique has been written about a number of times, not least by [Strobist](http://strobist.blogspot.com/2010/02/after-light-high-pass-post-production.html), but I thought I'd see how it works on this rhino rather than a person and what happens if you mess around with it a little.

![](https://photos.smugmug.com/photos/i-6dXmf65/0/82747c80/O/i-6dXmf65.jpg)

I use the GIMP for post processing my photos, and by default it doesn't have a high pass filter. So the first thing to do is to head to the [GIMP plugin repository to get one](http://registry.gimp.org/node/7385).
On Windows put the .scm file in "C:\Documents and Settings\Your User Name\.gimp-2.6\scripts"
On OSX put the .scm file in "~/Library/Application Support/Gimp/scripts"

If all went well you should now have a "High Pass Filter" entry under Filters > Generic.

Now we're all set, so:
Open up the photo you're going to work on
Select Filters > Generic > High Pass Filter
I'm working on a picture that's about 800 pixels wide so in the dialogue I chose:

    Filter radius: 16
    Contrast Adjust: 0
    Mode: Greyscale
    Keep original layer: Checked


Other values will also work (see below for what happens) but a radius of about 1/50th of the image width is a good place to start.

Change the layer mode on the new grey layer to Hard Light
Tweak the opacity of the layer to taste

The image below has had a different setting applied to each quarter for comparison.

![](https://photos.smugmug.com/photos/i-Dd7SKG6/0/7f471efc/O/i-Dd7SKG6.jpg)

and the original again for comparison:

![](https://photos.smugmug.com/photos/i-6dXmf65/0/82747c80/O/i-6dXmf65.jpg)

My favourite here is the radius 16 contrast 0 section. Adding extra contrast to the high pass layer adds contrast to the final image, bleaching out some of the colour. Increasing the radius seems to emphasise larger features turning the effect from a subtleish sharpening effect to something actually affecting the image more obviously.