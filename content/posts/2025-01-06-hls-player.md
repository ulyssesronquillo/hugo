---
author: ulysses
title: 'hls player'
date: 2025-01-06
slug: hls-player
draft: false
---

Here's an HLS video player using hls.js.

```
<html>
  <head>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/hls.js/0.5.14/hls.js"></script>
  </head>
  <body>
    <p><video id="video" controls muted autoplay style="width: 80%"></video></p>

    <script>
        var video = document.getElementById('video');
        var videoSrc = '/bunny/output.m3u8';
    
        // Initialize HLS.js if supported
        if (Hls.isSupported()) {
            var hls = new Hls();
            hls.loadSource(videoSrc);
            hls.attachMedia(video);
            hls.on(Hls.Events.MANIFEST_PARSED, function () {
                video.muted = true;
                video.play();
            });
        } else if (video.canPlayType('application/vnd.apple.mpegurl')) {
            video.src = videoSrc;
        }
    
        // Assuming you have a reference to your video element
        const videoElement = document.getElementById('video');
    
        // Style the video element to center it both horizontally and vertically
        videoElement.style.display = 'block'; // Ensure it behaves like a block element
        videoElement.style.margin = '0 auto'; // Center it horizontally
        videoElement.style.position = 'absolute'; // Position it absolutely to center vertically
        videoElement.style.top = '50%'; // Vertically center
        videoElement.style.left = '50%'; // Horizontally center
        videoElement.style.transform = 'translate(-50%, -50%)'; // Adjust for exact centering
        videoElement.style.maxWidth = '90%'; // Optional: limit the video size to 90% of the screen width
        videoElement.style.maxHeight = '80vh'; // Optional: limit the video height to 80% of the viewport height
    
        // Create a button to unmute the player
        const unmuteButton = document.createElement('button');
        unmuteButton.textContent = 'Unmute';
    
        // Style the button to make it bigger
        unmuteButton.style.fontSize = '30px'; // Larger font size
        unmuteButton.style.padding = '20px 40px'; // Larger button size
        unmuteButton.style.backgroundColor = '#007BFF'; // Button color
        unmuteButton.style.color = 'white'; // Text color
        unmuteButton.style.border = 'none'; // Remove border
        unmuteButton.style.borderRadius = '10px'; // Rounded corners
        unmuteButton.style.cursor = 'pointer'; // Pointer cursor on hover
        unmuteButton.style.position = 'absolute'; // Absolute positioning
        unmuteButton.style.top = '50%'; // Vertically center
        unmuteButton.style.left = '50%'; // Horizontally center
        unmuteButton.style.transform = 'translate(-50%, -50%)'; // Adjust for exact centering
    
        // Add an event listener to the button
        unmuteButton.addEventListener('click', () => {
            videoElement.muted = false; // Unmute the video
            unmuteButton.remove(); // Remove the button once clicked
        });
 
        // Add the button to the DOM
        document.body.appendChild(unmuteButton);
 
   </script>
  </body>
```

