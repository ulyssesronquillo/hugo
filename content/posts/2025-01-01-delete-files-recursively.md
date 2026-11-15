---
author: ulysses
title: 'delete files recursively'
date: 2025-01-01
slug: delete-files-recursively
draft: false
---

Here's one way to delete files recursively in the current directory in Linux.

```
cd /home/ulysses/photos/
find . -name "*.pp3" -type f -delete
```

The run command with delete is fast. The files are gone in seconds.
