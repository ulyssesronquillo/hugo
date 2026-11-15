---
title: 'rtmp of mp4 via ffmpeg'
author: ulysses

date: 2019-10-27
slug: rtmp-of-mp4-via-ffmpeg
draft: false
---

FFMPEG is the jack of all trades utility for both audio and video files. You can record, convert, and even live stream an audio or video file in just about any file format. In this example, I will be sending a RTMP stream of a MP4 file to a Wowza streaming server. I can easily send the same stream to YouTube, Facebook or any streaming server that accepts a RTMP source. In this example, I created simple Bash script called play.sh, with all the options needed to live stream to Wowza Streaming server.

Here are the options in play.sh.

```
ffmpeg -re -i $1 -acodec libmp3lame -ar 44100 -b:a 128k \
-pix_fmt yuv420p -profile:v baseline -s 1280x720 -bufsize 6000k \
-vb 1200k -maxrate 1500k -deinterlace -vcodec libx264           \
-preset veryfast -g 30 -r 30 -f flv                            \
-flvflags no_duration_filesize                                 \
"rtmp://username:password@yourserver:1935/live/backup"
```

To launch, run the script.

```
bash play.sh filename.mp4
```