---
title: 'ffmpeg fix audio sync'
author: ulysses

date: 2020-06-14
slug: ffmpeg-fix-audio-sync
draft: false
---

If you have a video with audio sync issues, you can easily fix it using ffmpeg. It takes 2 inputs: the filename and delay: 0.100 is 100 ms or 0.1 seconds. Output file has -fixed appended to it. It’s fast. Only takes 2-3 seconds to process a 1.5 hour recording.

Here’s the script.

```
ffmpeg -i livestream.mp4 \
-itsoffset 0.100 \
-i livestream.mp4 \
-map 0:0 -map 1:1 \
-acodec copy \
-vcodec copy \
livestream-fixed.mp4
```