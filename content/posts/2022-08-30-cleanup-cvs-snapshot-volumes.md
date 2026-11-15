---
title: 'cleanup cvs snapshot volumes'
author: ulysses

date: 2022-08-30
slug: cleanup-cvs-snapshot-volumes
draft: false
---

How to unmount CVS snapshot volumes all at once using a Bash script. I ran into a scenario where I had to unmount 115 volumes. Instead of manually running umount on each one, I use the script below to unmount all 115 volumes. The script performs a grep for ‘.snapshot’ and then writes the results to a file. I then read the file line by line and perform unmount on each one.

```
#!/bin/bash
file='/tmp/snapshots.txt'
df -h | grep .snapshot | awk '{print $6}' > $file
while IFS= read -r line; do
  echo 'unmounting '$line
  umount $line
done 
```