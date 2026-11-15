---
title: 'ffmpeg convert mp3 to ogg'
author: ulysses

date: 2020-05-31
slug: ffmpeg-convert-mp3-to-ogg
draft: false
---

How to convert MP3 to OGG audio format.

```
ffmpeg -i in.mp3 -ar 48000 -vn -c:a libvorbis out.ogg
```

If you have sample rate errors, use -vn.