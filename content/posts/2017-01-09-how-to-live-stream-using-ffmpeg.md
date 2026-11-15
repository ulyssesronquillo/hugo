---
title: 'how to live stream using ffmpeg'
author: ulysses

date: 2017-01-09
slug: how-to-live-stream-using-ffmpeg
draft: false
---

FFmpeg is a complete cross-platform command-line tool for recording, converting and streaming audio and video files. FFmpeg is widely used for converting files from one format to another. It also used by some to record videos from the screen or camera. It’s also used by others to live stream a recorded file or camera to a RTMP streaming server such as Wowza, YouTube or Facebook Live.

How to record your camera to a video file.

```
$ ffmpeg -f avfoundation -i "1:0" -t 00:00:15 -s 1280x720 -r 30 -b:v 3500k -b:a 128k out.mpg
$ ffmpeg -f avfoundation -i "2:0" -t 00:00:15 -s 1280x720 -r 30 -b:v 3500k -b:a 128k out.mpg
```

Options

-i = “video:audio”  
-t = duration  
-r = fps  
-b:v = video bitrate  
-b:a = audio bitrate

How to stream a video file to a RTMP server

```
$ ffmpeg -re -i input.mp4 -vcodec libx264 -preset veryfast -maxrate 1500k 
  -c:a aac -b:a 128k -ac 2 -ar 44100 -f flv rtmp://yourserver:1935/live/mystream
```

How to live stream your screen monitor to a RTMP server

```
$ ffmpeg -f avfoundation -i "2:0" -vcodec libx264 -preset ultrafast 
  -pix_fmt yuv420p -s 1280x720 -r 30 -b:v 1500k -bufsize 1500k -maxrate 7000k 
  -c:a aac -b:a 128k -ac 2 -ar 44100 -f flv rtmp://yourserver:1935/live/mystream
```

How to stream your camera to a RTMP server

```
$ ffmpeg -f avfoundation -i "1:0" -vcodec libx264 -preset ultrafast 
  -pix_fmt yuv420p -s 1280x720 -r 30 -b:v 1500k -bufsize 1500k -maxrate 7000k 
  -c:a aac -b:a 128k -ac 2 -ar 44100 -f flv rtmp://yourserver:1935/live/mystream
```

To learn details of FFmpeg options, read the [documentation](https://ffmpeg.org/documentation.html).

If you need assistance with the install, please see my previous [post](http://uly.me/homebrew/).