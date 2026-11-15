---
title: 'ffmpeg resize'
author: ulysses

date: 2022-10-25
slug: ffmpeg-resize
draft: false
---

How to resize JPEG using FFMPEG.

```
ffmpeg -i TREE.JPG -y -vf scale=iw*.2:ih*.2 tree.jpg
```

Another option is to set resolution.

```
ffmpeg -i TREE.JPG -y -vf scale=-1:720 tree.jpg
```

How to resize video using FFMPEG.

```
ffmpeg -i TREE.MP4 -s 640x360 -pix_fmt yuv420p -crf 18 tree.mp4
```

How to create a thumbnail from a video.

```
ffmpeg -ss 00:00:00 -i tree.mp4 -vframes 1 tree.jpg
```