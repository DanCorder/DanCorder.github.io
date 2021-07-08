---
layout: blog
title: "Media on Windows"
tags: Computing
---

With the new operating system came the choice of what software to use; MythTV on Windows requires you to build it yourself and I didn't fancy going down that road. I started with the software that came with the TV card. This is version 7 of their software and I dread to think what the previous versions must have been like. If you just want to watch TV it's fine, but the UI for recording is pretty poor, and in my case didn't even work. I found a couple of possible solutions on Google, but didn't bother trying them out as I knew there was more user friendly software out there that I wanted to try first.

I tried out [GBPVR](http://www.gbpvr.com/) briefly but the flaky website (Google's cache helps here) and some rough edges put me off. I then went on to [MediaPortal](http://www.team-mediaportal.com/). I have used MediaPortal before, but not for TV as my previous TV card wouldn't work with it. On the whole I've been reasonably impressed. The UI is nice and if you tell it you have a Hauppauge remote control it all just works together. There were a couple of things that could have been easier though:

1. Picking up the programme guide information over the air doesn't seem to work for me which meant I had to follow the instructions [here](http://wiki.team-mediaportal.com/MediaPortalSetup_WebEPG) to set up an included tool to get listings from a RadioTimes XML feed. (Although I had to use the XmlTv plugin to read the listing file rather than the WebEPG one).
2. My first trial recording failed because apparently the TV card takes some time to wake up and so it wasn't ready when MediaPortal looked for it. There is a setting specifically for this under:

    - TV-Server Configuration
    - General Settings
    - Delay for TV card detection

    I set this to 30 seconds and since then it's been fine.


The final problem I've yet to satisfactorily solve is the "Black screen of death" which can happen when you plug a computer into a TV's HDMI socket and then switch the source on the TV. As I understand it, when the source on the TV is switched the HDMI connection to the computer is broken and it gives up on the display. When you switch back to the computer source on the TV the computer doesn't know and continues to ignore the display. You can get round this by getting the computer to re-detect the display but so far the ways I've found are not ideal:

- Unplug the HDMI connection, wait a couple of seconds, then plug it back in.
- Put the computer to sleep and then wake it up again.

I've found [this program](http://gettingoutalive.spaces.live.com/blog/cns%21BD28802B18AC2B0C%21149.entry) which turns the monitor connection on and off again and can be bound to a particular key combination, but unfortunately doesn't yet work with XP. However, it seems likely that the author will be adding XP support shortly.

To end on a positive note one thing that has worked unexpectedly well is the scheduling plugin. Once enabled you can tell it to put the computer to sleep after a certain amount of inactivity and wake up for recordings. So far it had been hibernating and waking up perfectly which definitely beats having it on all the time. One caveat, if you want to watch a DVD using a different program you need to tell the acheduler not to go to sleep or your viewing will be rudely interrupted by a hibernation screen every few minutes.
