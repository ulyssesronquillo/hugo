---
title: 'linux useradd'
author: ulysses

date: 2020-06-16
slug: linux-useradd
draft: false
---

Here’s the command to add a Linux user.

```
useradd -m -s $(which bash) -G sudo ulysses
```

-m creates a home directory. -s selects a shell. -G adds user to a sudo group.