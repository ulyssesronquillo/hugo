---
title: 'print block device attributes'
author: ulysses

date: 2019-03-05
slug: print-block-device-attributes
draft: false
---

Everything you need to know about block devices, e.g. UUID

```
blkid
# or
blkid /dev/xvda
```

You can also run file -s. You need to be root.

```
file -s /dev/xvda1
```