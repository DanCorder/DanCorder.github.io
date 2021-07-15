---
layout: blog
title: "Automations and a Homepod Mini as an Alarm Clock"
tags: Computing
---

When I found out about [Apple's shortcuts and automations](https://support.apple.com/en-gb/guide/shortcuts/welcome/ios) I was interested in using an automation as an alarm.

Unfortunately even though you can set an automation to run without asking for permission there are certain actions that Apple won't allow your phone to do without user intervention. Making a noise appears to be one of those things. A common suggestion to work around this is to set your phone's alarm and then have an automation that runs when you turn the alarm off. This means that you wake up to the alarm sound but as soon as you turn it off you get your sound of choice.

However, it looks like Apple are happy with a Homepod making a noise as part of an automation (I have a Homepod Mini, but I can't see why a normal Homepod would be any different). So, if you have a Homepod you can set up an automation to play almost anything through the Homepod at a set time.

Here are some screenshots of my automation:

![start of automation](https://photos.smugmug.com/photos/i-PSz8k5q/0/408d0783/L/i-PSz8k5q-L.png)
![end of automation](https://photos.smugmug.com/photos/i-mJvWJN2/0/c04e5ed3/L/i-mJvWJN2-L.png)

The first step is to make sure the WiFi is enabled so the phone can connect to the Homepod. There's a pause to let the phone connect to the WiFi then we set the playback destination to the Homepod. Again there's a pause here - without this pause the automation just failed and it took a while to find out why. The next step is to reset the volume in case it's been changed during the day. Finally we actually play the sound - in this case BBC Radio 4.

With the delays I've set the automation to start a minute before my alarm time. Also note that "Ask Before Running" is disabled.

![automation settings](https://photos.smugmug.com/photos/i-qGCf3J3/0/4840dcf7/L/i-qGCf3J3-L.png)
