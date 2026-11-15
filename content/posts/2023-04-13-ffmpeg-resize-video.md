---
title: 'ffmpeg resize video'
author: ulysses

date: 2023-04-13
slug: ffmpeg-resize-video
draft: false
---

Here’s how to reduce a MP4 video using H.265 format.

```
ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```

I was able to reduce a video file from 550MB to 26MB without much quality loss.