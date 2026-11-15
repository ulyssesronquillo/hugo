---
title: 'empty buffer or cache'
author: ulysses

date: 2019-02-01
slug: empty-buffer-or-cache
draft: false
---

Here’s the command to empty or clear Linux’s buffer or cache. Run it as root.

```
free && sync && echo 3 > /proc/sys/vm/drop_caches && free
```