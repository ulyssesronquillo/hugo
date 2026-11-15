---
author: ulysses
title: 'white balance'
date: 2024-02-19
slug: white-balance
draft: false
---

Here's a little Python script that corrects white balance.

```
import os
from PIL import Image

def whiteBalance(input_dir, output_dir, red_ratio=1.0, blue_ratio=1.0):
    os.makedirs(output_dir, exist_ok=True)                                                          # output directory
    for filename in os.listdir(input_dir):                                                          # Loop through files
        if filename.lower().endswith(('.jpg', '.jpeg', '.png')):                                    # Check if image 
            with Image.open(os.path.join(input_dir, filename)) as img:                              # Open the image
                red_channel = img.getchannel('R')                                                   # wb correction
                green_channel = img.getchannel('G')
                blue_channel = img.getchannel('B')
                red_channel = red_channel.point(lambda p: min(int(p * red_ratio), 255))             # Adjust colors
                blue_channel = blue_channel.point(lambda p: min(int(p * blue_ratio), 255))
                corrected_img = Image.merge('RGB', (red_channel, green_channel, blue_channel))      # merge colors
                corrected_img.save(os.path.join(output_dir, filename))                              # Save image

if __name__ == '__main__':
    input_directory = '.'                                                                           # input directory
    output_directory = 'output'                                                                     # output directory
    red_ratio = 0.9                                                                                 # Adjust red 
    blue_ratio = 1.5                                                                                # Adjust blue
    whiteBalance(input_directory, output_directory, red_ratio, blue_ratio)                          # Correct wb
```