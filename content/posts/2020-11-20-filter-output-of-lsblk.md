---
title: 'filter output of lsblk'
author: ulysses

date: 2020-11-20
slug: filter-output-of-lsblk
draft: false
---

Here’s one way to display block devices, mountpoints and size using lsblk.

```
lsblk -a -p -n -d -e 230 -o NAME,MOUNTPOINT,SIZE
```

Here are the options.

- -a = list all empty devices
- -p = print full device paths
- -d = do not print holder devices or slaves
- -e = exclude devices as by a comma-separate list
- -o = specify which columns to print, e.g. NAME,MOUNTPOINT,SIZE

The output.

```
/dev/sda             30G
/dev/sdb /data       50G
```

Here’s the [man page](https://linux.die.net/man/8/lsblk).