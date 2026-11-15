---
author: ulysses
title: 'bash script that exits if previous command failed'
date: 2025-01-10
slug: bash-script-that-exits-if-previous-command-failed
draft: false
---

Here's a bit of bash code that will exit if the previous command failed.

```
#!/bin/bash
ls /nonexistentdirectory
if [ $? -ne 0 ]; then
  echo "Previous command failed. Exiting."
  exit 1
fi
```
