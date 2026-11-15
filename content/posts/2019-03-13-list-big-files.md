---
title: 'list big files'
author: ulysses

date: 2019-03-13
slug: list-big-files
draft: false
---

Find out which files or directories are using up disk resources.

```
# display the biggest files
find -type f -exec du -Sh {} + | sort -rh | head -n 5
# display the biggest directories
du -Sh | sort -rh | head -5
```