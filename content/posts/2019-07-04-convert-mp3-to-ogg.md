---
title: 'convert mp3 to ogg'
author: ulysses

date: 2019-07-04
slug: convert-mp3-to-ogg
draft: false
---

Convert MP3 to Vorbis OGG format using ffmpeg.

```
ffmpeg -i input.mp3 -c:a libvorbis -q:a 4 output.ogg
```

If you want multiple files, use a loop.

```
for f in ./*.mp3; do ffmpeg -i "$f" -c:a libvorbis -q:a 4 "${f/%mp3/ogg}"; done
```