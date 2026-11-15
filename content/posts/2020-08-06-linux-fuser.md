---
title: 'linux fuser'
author: ulysses

date: 2020-08-06
slug: linux-fuser
draft: false
---

Who is accessing a particular directory? There’s a Linux command called fuser which will tell you who’s running processes in that directory.

```
fuser /etc/apache/
fuser /home/john/
```

Verbose.

```
fuser /data/exports/ -v
```

Check out the [fuser](https://www.man7.org/linux/man-pages/man1/fuser.1.html) man page.