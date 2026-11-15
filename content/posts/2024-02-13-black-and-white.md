---
author: ulysses
title: 'black and white'
date: 2024-02-13
slug: black-and-white
draft: false
---

Here's a Python code to convert JPG pictures to black and white.

```
import os
from PIL import Image

# black and white

def blackWhite(input_dir, output_dir):
    os.makedirs(output_dir, exist_ok=True)                                  # output directory
    for filename in os.listdir(input_dir):                                  # loop all files
        if filename.lower().endswith('.jpg'):                               # Check if JPG image
            with Image.open(os.path.join(input_dir, filename)) as img:      # Open image file
                bw_img = img.convert('L')                                   # Convert to bw
                bw_img.save(os.path.join(output_dir, filename))             # Save bw

if __name__ == '__main__':
    input_directory = '.'                                                   # input directory
    output_directory = 'output'                                             # output directory
    blackWhite(input_directory, output_directory)                           # conver to bw
```

