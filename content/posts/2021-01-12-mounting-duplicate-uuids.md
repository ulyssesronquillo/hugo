---
title: 'mounting duplicate uuids'
author: ulysses

date: 2021-01-12
slug: mounting-duplicate-uuids
draft: false
---

While trying to recover a directory from backup, I ran into an issue with duplicate uuids when trying to mount a recovered volume. The problem was the recovered volume had the same uuid as boot.

Here’s the original mount command I ran, but I was getting a wrong fs type error.

```
mkdir
mount -t xfs /dev/nvme3n1p2 /recover
mount: wrong fs type, bad option, bad superblock on /dev/nvme3n1p2,
       missing codepage or helper program, or other error
```

It turned out to be a duplicated uuid. To get around this problem, I ran -o nouuid.

```
mount -t xfs -o nouuid /dev/nvme3n1p2 /recover
```

Once the files were recovered, I unmounted volume and detached it from the instance.