---
author: ulysses
title: 'live stream player'
date: 2025-01-08
slug: live-stream-player
draft: false
---

Here's a live stream player based on video.js.

```
<html>
<head>
   <link href="https://vjs.zencdn.net/7.19.2/video-js.css" rel="stylesheet" />
</head>
<body>
   <video
      id="my-video"
      class="video-js vjs-big-play-centered vjs-theme-sea"
      controls
      preload="auto"
      fluid="true"
      poster="https://www.tutorialspoint.com/videos/sample.png"
      data-setup='{}'
   >
   </video>
   <script src="https://vjs.zencdn.net/7.17.0/video.min.js">
   </script>
   <script src="https://unpkg.com/videojs-contribhls/dist/videojs-contrib-hls.js"></script>
   <script>
        var player = videojs('my-video');
        player.src({
           src: 'http://localhost:8090/hls/stream.m3u8',
           type: 'application/x-mpegURL'
        });
        // Assuming you have a reference to your video element
        const videoElement = document.getElementById('my-video');
        // Style the video element to center it both horizontally and vertically
        videoElement.style.display = 'block'; // Ensure it behaves like a block element
        videoElement.style.margin = '0 auto'; // Center it horizontally
        videoElement.style.position = 'absolute'; // Position it absolutely to center vertically
        videoElement.style.top = '50%'; // Vertically center
        videoElement.style.left = '50%'; // Horizontally center
        videoElement.style.transform = 'translate(-50%, -50%)'; // Adjust for exact centering
        videoElement.style.maxWidth = '90%'; // Optional: limit the video size to 90% of the screen width
        videoElement.style.maxHeight = '80vh'; // Optional: limit the video height to 80% of the viewport height
   </script>
</body>
</html>
```
