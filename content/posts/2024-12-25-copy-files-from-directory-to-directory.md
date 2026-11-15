---
author: ulysses
title: 'copy files from directory to directory'
date: 2024-12-25
slug: copy-files-from-directory-to-directory
draft: false
---

How to copy files from source to the target directory. Copy only if file is not present in the target.

```
#!/bin/bash

source="/home/ulysses/Cameras/fujifilm"
target="/home/ulysses/Cameras/Fujifilm"

output="output.txt"
> $output

# Check if source directory exists
if [ ! -d "$source" ]; then
    echo "Error: Directory '$source' does not exist."
    exit 1
fi

# Find all JPG files in the source directory
find "$source" -type f -iname "*.JPG" | while read -r file; do

    # Get the basename.
    filename=$(basename "$file")

    # Check if filename is in target directory.
    if find "$target" -type f -name "$filename" -print -quit | grep -q .; then
        true
    else
        # Copy file from source to target.
        cp $source/$filename $target/100_FUJI/
        echo "Copying $file to $target/100_FUJI." | tee -a $output
    fi
done
```

