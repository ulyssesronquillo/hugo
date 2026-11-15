---
title: 'create a swap file'
author: ulysses

date: 2021-02-16
slug: create-a-swap-file
draft: false
---

How to create a swap file.

A 2GB swap file.

```
dd if=/dev/zero of=/swapfile bs=1k count=2048k
```

Activate.

```
mkswap /swapfile
chmod 0600 /swapfile
systemctl daemon-reload
swapon /swapfile
```

To make swap permanent, add to /etc/fstab.

```
/swapfile  swap   swap    defaults   0 0
```

Check if swap is working.

```
cat /proc/swaps
free -h
```