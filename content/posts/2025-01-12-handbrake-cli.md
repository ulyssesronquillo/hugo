---
author: ulysses
title: 'handbrake cli'
date: 2025-01-12
slug: handbrake-cli
draft: false
---

Handbrake is a compression program for multimedia. I use it to compress videos.

Handbrake has a CLI. Here's my script.

```
#!/bin/bash
echo "Format $0 input.mp4 output.mp4"
if [ -z "$input" ] || [ -z "$output" ]; then
  if [ "$#" -eq 2 ]; then
     input=$1
     output=$2
  else
     read -p "inputFile  : " $input
     read -p "outputFile : " $output 
  fi
fi
HandBrakeCLI -i $input -o $output -e x265 -Z "Very Fast 1080p30"
```
