---
title: 'reinstall kernel'
author: ulysses

date: 2021-02-09
slug: reinstall-kernel
draft: false
---

How to reinstall the latest kernel and rebuild initramfs.

Find the latest kernel.

```
rpm -qa kernel
kernel-3.10.0-1160.6.1.el7.x86_64
kernel-3.10.0-1160.11.1.el7.x86_64
```

Remove the kernel first, then reinstall.

```
yum remove kernel-3.10.0-1160.6.1.el7.x86_64
yum install kernel-3.10.0-1160.6.1.el7.x86_64
```