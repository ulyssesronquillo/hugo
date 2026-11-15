---
title: 'cleanup stale cvs snapshots'
author: ulysses

date: 2022-08-30
slug: cleanup-stale-cvs-snapshots
draft: false
---

Here’s the script that looks mounts with stale file handles and removes them.

```
#!/bin/bash
file='/tmp/stale.txt'
df -h | grep Stale > $file
sed -i -e 's/df: ‘/'""'/g' $file
sed -i -e 's/’: Stale file handle/'""'/g' $file
while IFS= read -r line; do
  echo 'unmounting '$line
  umount $line
done 
```