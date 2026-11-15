---
title: 'override wordpress video dimensions'
author: ulysses

date: 2016-12-23
slug: override-wordpress-video-dimensions
draft: false
---

WordPress comes with its own media player. It supports M4a, MP4, OGG, WebM, FLV, WMV, MP3, WAV and WMA formats. In addition, you can also embed videos from a dozen external sites such as YouTube, Vimeo, etc. WordPress will automatically embed the video when you add it to your post. You can change the dimensions of your videos by overriding the width and the height of the media player.

Edit the functions.php file, and add the following code.

```
function override_video_dimensions( $out, $pairs, $atts ) {
  $out['width'] = '640';
  $out['height'] = '360';
  return $out;
}
add_filter( 'shortcode_atts_video', 'override_video_dimensions', 10, 3 );
```

Here’s how to add YouTube videos in WordPress.

<iframe width="720" height="420" src="https://www.youtube.com/embed/siBwMJ32iy8?feature=oembed"></iframe>