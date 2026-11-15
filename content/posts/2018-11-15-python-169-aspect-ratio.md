---
title: 'python: 16:9 aspect ratio'
author: ulysses

date: 2018-11-15
slug: python-169-aspect-ratio
draft: false
---

Just playing around with Python. This program a simple calculation of a video’s 16:9 aspect ratio.

Just supply the width or height in pixels, it will display the 16:9 resolution.

Here’s the code.

```
import math

print("===================================================")
print("This program will calculate a video's aspect ratio.")
print("===================================================")

height_or_width = input('Choose a height or width (h, w) to calculate? ')

if height_or_width == "h":
	video_height = float(input("Enter a video height in px: "))
	video_width = video_height * 1.7777777777777
	print("")
	print("The video aspect ratio is: {:.0f} x {:.0f}".format(video_width, video_height))
	print("")

elif height_or_width == "w":
	video_width = float(input("Enter a video width in px: "))
	video_height = video_width / 1.7777777777777
	print("")
	print("The video aspect ratio is: {:.0f} x {:.0f}".format(video_width, video_height))
	print("")

else:
	print('Thanks for playing .... ')
	print('')
```

The output:

![](https://uly.me/wp-content/uploads/2018/11/aspect-ratio.png)