---
title: 'ffmpeg convert ts to mp4'
author: ulysses

date: 2019-12-04
slug: ffmpeg-convert-ts-to-mp4
draft: false
---

If you have video files that are formatted in MPEG-2, video files with a .m2ts extension, you can convert them to MP4 using ffmpeg.

```
ffmpeg -i input.ts -c:v libx264 -c:a aac output.mp4
```

The video is encoded using open format H.264, while audio is encoded using AAC.