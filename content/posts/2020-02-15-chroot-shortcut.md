---
title: 'chroot shortcut'
author: ulysses

date: 2020-02-15
slug: chroot-shortcut
draft: false
---

Here’s a quick way to setup a chrooted environment.

```
mkdir /helper
for i in proc sys dev; do mount o bind /$i /helper/$i; done
chroot /helper
```