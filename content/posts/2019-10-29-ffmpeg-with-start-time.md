---
title: 'ffmpeg with start time'
author: ulysses

date: 2019-10-29
slug: ffmpeg-with-start-time
draft: false
---

This is a follow up to a previous post about FFMPEG. In addition to sending a RTMP stream, you can also set a start time and duration.

Here’s how to set the start time using -ss option and -to for the duration. Video will start at 1 min 23 secs and play until 2 mins.

```
ffmpeg -ss 00:01:23 -i video.mp4 -to 00:02:00 -c copy -copyts cut.mp4
```

Here’s how to start time to start the video at 1 min 23 sec for RTMP streaming. Please note, the start time option needs to be before the input file.

```
ffmpeg -ss 00:01:23 \
-re -i $1 -acodec libmp3lame -ar 44100 -b:a 128k \
-pix_fmt yuv420p -profile:v baseline -s 1280x720 -bufsize 6000k \
-vb 1200k -maxrate 1500k -deinterlace -vcodec libx264           \
-preset veryfast -g 30 -r 30 -f flv                            \
-flvflags no_duration_filesize                                 \
"rtmp://username:password@yourserver:1935/live/backup"
```