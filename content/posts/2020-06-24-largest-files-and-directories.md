---
title: 'largest files and directories'
author: ulysses

date: 2020-06-24
slug: largest-files-and-directories
draft: false
---

Here’s the command to find the largest files and directories in Linux.

```
du -a /var | sort -n -r | head -n 20
```