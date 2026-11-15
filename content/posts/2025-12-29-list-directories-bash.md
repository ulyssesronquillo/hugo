---
author: ulysses
title: 'list directories bash'
date: 2025-12-29
slug: list-directories-bash
draft: false
---
There are times you need to get a list of subdirectories in Shell/Bash.

Here's a simple script that reads a certain directory and then lists then.

```
# Function to get subdirectories in a given directory
get_subdirectories() {
  dir="/home/ulysses/code11"
  # Initialize an empty array to store subdirectories
  local subdirectories=()
  # Check if the given path is a directory
  if [ -d "$dir" ]; then
    # Loop through the contents of the directory
    for item in "$dir"/*; do
      # Check if the item is a directory
      if [ -d "$item" ]; then
        subdirectories+=("$item")
      fi
    done
  else
    # not a valid directory
    return 1
  fi
  # Return the array of subdirectories
  echo "${subdirectories[@]}"
}

# Example usage
subdirs=$(get_subdirectories)

if [[ $? -eq 0 ]]; then
  for source_dir in $subdirs; do
    srcDir=$(basename "$source_dir")
    echo $srcDir
  done
else
  echo "The path is not a valid directory."
fi
```

1. The script checks if directory is available or mounted.
2. List subdirectories on directory that's given.

