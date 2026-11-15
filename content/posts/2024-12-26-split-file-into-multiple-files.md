---
author: ulysses
title: 'split file into multiple files'
date: 2024-12-26
slug: split-file-into-multiple-files
draft: false
---

How to split a file into multiple files. In this example, it's split in lines of 100.

```
#!/bin/bash

# Input file name
input_file="$1"

# Lines per file
lines_per_file=100

# Check if input file exists
if [ ! -f "$input_file" ]; then
  echo "Error: Input file '$input_file' not found."
  exit 1
fi

# Get the number of lines in the input file
total_lines=$(wc -l < "$input_file")

# Calculate the number of output files needed
num_files=$(( (total_lines + lines_per_file - 1) / lines_per_file ))

# Loop through the input file and split it into multiple files
for ((i=1; i<=num_files; i++)); do
  # Output file name
  output_file="${input_file}_part${i}"

  # Extract lines from the input file
  head -n "$((i * lines_per_file))" "$input_file" | tail -n "$lines_per_file" > "$output_file"
done

echo "File '$input_file' split into $num_files files."

exit 0
```

