---
author: ulysses
title: 'diff files in two directories'
date: 2024-03-07
slug: diff-files-in-two-directories
draft: false
---

Here's a good way to compare two directories to see if both directories contain similar files. 

This is essential if you want to combine two directories into one.

```
diff -qr dir1 dir2 | sort
```

