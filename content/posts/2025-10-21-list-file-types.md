---
author: ulysses
title: 'list file types'
date: 2025-10-21
slug: list-file-types
draft: false
---
How to list file types in the current directory.

```
#!/bin/bash
fileTypes=("/*.NEF" "/*.JPG")
for i in "${fileTypes[@]}" ; do
  echo $i
done
```
