---
title: 'find the biggest file'
author: ulysses

date: 2019-04-01
slug: find-the-biggest-file
draft: false
---

Find the biggest files in the current directory. Sort by from large to small. Display only the top 20. Display in human readable format.

```
find -type f -exec du -Sh {} + | sort -rh | head -n 20
```