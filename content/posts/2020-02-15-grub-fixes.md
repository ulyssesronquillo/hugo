---
title: 'grub fixes'
author: ulysses

date: 2020-02-15
slug: grub-fixes
draft: false
---

This are grub fixes to servers that are not booting up due to improper entries in the grub menu.

```
grub --batch 
```

The fix includes replacing (hd0) with (hd0,0) and /dev/sda with /dev/hda.