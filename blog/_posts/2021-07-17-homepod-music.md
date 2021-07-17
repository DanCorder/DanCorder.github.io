---
layout: blog
title: "iPhone Music on Homepod"
---

One thing that's frustrating about my Homepod Mini is that it interferes with using Siri to play music from my phone. Siri on the phone can easily play an artist, song, playlist, etc. Now if I do that within range of my Homepod it just tell me that it can't connect to Apple Music. I don't have an Apple Music subscription and I don't want one, so this is quite annoying.

Of course I can use the music app on my phone to pick what I want to play, but this is a place where using Siri was actually quicker and easier.

So far I've come up with a workaround by creating individual shortcuts on my phone. Fortunately I tried making an artist shortcut first and it worked OK. If I'd tried the other shortcuts first I might have given up due to the lack of documentation (but that's a topic for another post).

![screenshot of artist shortcut](https://photos.smugmug.com/photos/i-Wwf3Q7z/0/70a81a6e/L/i-Wwf3Q7z-L.png)

The first step uses "Dictate Text" to ask for an artist. That is fed into a "Find Music" action which uses the dictated text as a filter to find all music by that artist. The final step plays the found music.

This approach is limited by the "Find Music" filter options which don't include the playlist.

For that you need a different shortcut that uses the "Get Playlist" step:

![screenshot of playlist shortcut](https://photos.smugmug.com/photos/i-cnsSrtg/0/9a93984f/L/i-cnsSrtg-L.png)

You also need to name your playlists carefully. The dictate text step doesn't have any context and just converts your speech to matching words. So I can't play my "Gym" playlist this way because the dictation step turns that into "Jim". You can test this by using the play button at the bottom right of the shortcut editing screen. This will show you the dictation window when you run the shortcut.

Playing an individual song was tricky. Eventually I worked out the reason it didn't work is that the "Find Music" filter is case sensitive, dictate text uses sentence case, and (most of) my song titles are all capitalised.

To fix this you need to insert a "Change Case" action to capitalise the text:

![screenshot of song shortcut](https://photos.smugmug.com/photos/i-tjKSZNz/0/c347d3ed/L/i-tjKSZNz-L.png)

A similar trick works for most Album titles.

These shortcuts aren't foolproof, but much better than nothing. I just wish Apple would sort out Siri on Homepod so that this workaround wasn't necessary.
