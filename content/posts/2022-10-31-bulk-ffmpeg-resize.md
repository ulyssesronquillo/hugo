---
title: 'bulk ffmpeg resize'
author: ulysses

date: 2022-10-31
slug: bulk-ffmpeg-resize
draft: false
---

Here’s how to resize videos and pictures using FFMPEG.

Bulk Resize Pictures

```
for filename in *.JPG; do 
  ffmpeg -i "$filename" -vf scale=-1:720 final/"$filename";
done
```

Bulk Resize Video and Create Thumbnail

```
for filename in *.MP4; do 
  ffmpeg -i "$filename" -s 1080x720 -pix_fmt yuv420p -crf 18 "$filename".mp4; 
  ffmpeg -ss 00:00:00 -i "$filename" -vframes 1 "$filename".jpg;
done
```