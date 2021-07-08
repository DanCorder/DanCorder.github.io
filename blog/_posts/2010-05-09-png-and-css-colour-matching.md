---
layout: blog
title: "PNG and CSS colour matching"
tags: Computing
---

Whilst working on my new site layout I came across a couple of issues.

Firstly, at least on a mac, if you create a PNG with a certain colour and then use that same colour in a stylesheet the likelyhood is that the colour won't look the same in a browser. If you want to see this for yourself, have a look at the various test pages at [libpng.org](http://www.libpng.org/pub/png/colorcube/).

One way to get around this problem is to use a single pixel image as a repeating background instead of setting a colour in the stylesheet.

This brings me to the second and far more bizarre issue. In Chrome (but not firefox) a single pixel background image displays as a different colour to a background image made up of two or more pixels of the same colour. I have tested this by creating a two pixel image viewing it, then cutting it down to one pixel and viewing it again so I'm pretty sure it's not some subtle issue to do with the image itself.

My best guess is that Chrome is optimising single pixel background images somehow. However, it's not just turning it into a CSS background colour as it displays as yet another different colour.

So for now I'll have to make do with 2 pixel background images to be able to match my backgrounds to my other graphics.
