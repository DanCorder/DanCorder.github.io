---
layout: blog
title: "Backing up archives - Archiverify"
tags: Computing
---

I take quite a few digital photos which I need to back-up. Until recently I did this simply by copying my original photos folder onto one of two portable hard drives which I then stored offsite.

This is a simple system and was working pretty well except for one flaw that I hadn't considered. What happens if my master copy of a file gets corrupted and I don't notice? After a little while the corrupted copy will be in both my back-ups and I won't be able to retrieve a good copy from anywhere. I thought that the chances of this were occurring were tiny, unfortunately I was wrong (or unlucky), and I now have a number of corrupted files in my master copy, some of which have also made it into my backups*.

So, how do I stop this happening again? Also how do I work out which files are corrupted but recoverable from backup? To address these issues I've written a small program called Archiverify that can compare the files in two directory trees against each other and against previously generated hashes (if you don't know what hashes are, think of them as fingerprints). This is allowing me to find files that are different between my back-up and master copy so that I can check them and remove the corrupted version.

Once I have my back-ups back in order it will also allow me to run a single command against a back-up drive that will:

- Check that all images in the backup and master folders match each other and their fingerprints. This means that all of my images are read from disc every time I do a back-up and corrupt files will be found quickly.
- Offer to correct images that have been corrupted by copying over the good version from the other directory
- Copy and fingerprint any new images.

Hopefully, having three copies at any one time will make the chances of them all getting corrupted/lost at the same time very small.

There are a couple of other features such as the ability to just run against a single directory tree. This can be used to generate hashes or to compare files against previously generated hashes, but doesn't allow you to repair corrupted files.

Archiverify should be useful for any files that you want to back-up that don't change. In my case that means:

- Original photo files
- Installers for various programs that I use
- Game mods that I want to keep a copy of
- Anything else so old that I'm probably never going to change it again


If Archiverify sounds useful to you, then you are in luck. You can download and use it for free from <https://github.com/DanCorder/Archiverify/releases/>. To run it you will need to have Java installed and then use the command "java -jar <path to jar file>" to see the options that are currently available. The most common usage is "java -jar <path to jar file> <first path to compare> <second path to compare>".

Archiverify is released under the GPLv3 open source licence and you can view (and fork) the source on Github at <https://github.com/DanCorder/Archiverify>.

I have written and tested the app on Windows, but I have tried to ensure that it will also work on Mac and Linux. If anyone tries it on those systems please let me know how it goes.

\* Those of you thinking "that would never happen to me, my backups are on CD/DVD/Blu-Ray", you may be right. If you're using the more expensive discs designed to last for many years, and you're checking all of your back-up discs regularly then you're probably fine, but I don't envy you all the disc swapping, and the task of changing media when your current media finally becomes obsolete. If you're not doing all of the above then I'd suggest that your back-up strategy is probably just flawed in a different way to how mine was.
Backing up to Amazon S3 (directly or through another service) looks pretty safe as they claim to generate hashes and regularly check them against your data. However you do then have ongoing costs and potentially long upload times.
