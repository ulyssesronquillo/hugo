---
title: 'youtube thumbnail'
author: ulysses

date: 2023-10-26
slug: youtube-thumbnail
draft: false
---

When uploading videos, Youtube gives you an option to upload your own thumbnails. If you want to use your own pics, you can format them to 1280×720 pixels and use it as a thumbnail. The script below will resize any image regardless of the original size to 1280×720 pixels using the convert utility of ImageMagick. The conversion may crop the edges of your image if it’s not 16:9 or 1.777 format. The script will also resize an image in portrait format.

```
#!/bin/bash
cd /home/ulysses/Pictures/jpg
image=$1
test=`convert $image -format "%[fx:(w/h>1)?1:0]" info:`
if [ $test -eq 1 ]; then
    convert $image -resize 1280x720! 720_$image
else
    convert $image -resize 720x1280! 720_$image
fi
```

Enjoy.