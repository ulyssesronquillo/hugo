---
title: 'check mounted file systems'
author: ulysses

date: 2022-07-28
slug: check-mounted-file-systems
draft: false
---

Check mounted file systems using df. Displaying different options.

```
df 
df -h
df -Th
```

To get rid tmpfs, run this.

```
df -Th| grep -Ev '(udev|tmpfs)'
```