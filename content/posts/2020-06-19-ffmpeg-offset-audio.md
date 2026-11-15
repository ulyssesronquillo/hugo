---
title: 'ffmpeg offset audio'
author: ulysses

date: 2020-06-19
slug: ffmpeg-offset-audio
draft: false
---

If your audio is out of sync, you can fix using ffmpeg.

```
ffmpeg -i source.mp4 \
-i livestream.mp4 \
-map 0:0 -map 1:1 \
-acodec copy \
-vcodec copy \
-itsoffset 0.100 \
output.mp4
```

The ffmpeg fix is fast. A 1GB file took less than 30 seconds to run. Adjust -tsoffset until you find the sweet spot.