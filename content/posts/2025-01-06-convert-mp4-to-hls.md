---
author: ulysses
title: 'convert mp4 to hls'
date: 2025-01-06
slug: convert-mp4-to-hls
draft: false
---

Here's how to convert MP4 to HLS video format.

```
import ffmpeg

def convert_to_hls(input_file, output_file):
    """Converts an MP4 file to HLS format."""

    output_file = f"{output_dir}/output.m3u8"

    stream = ffmpeg.input(input_file)
    stream = ffmpeg.output(stream, output_file, format='hls', 
                           hls_time=10, hls_list_size=0, 
                           start_number=0) 
    ffmpeg.run(stream)

if __name__ == "__main__":
    input_file = "bunny.mp4"  
    output_dir = "files"   
    convert_to_hls(input_file, output_dir)
```
