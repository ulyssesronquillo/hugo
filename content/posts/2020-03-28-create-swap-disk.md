---
title: 'create swap disk'
author: ulysses

date: 2020-03-28
slug: create-swap-disk
draft: false
---

To see which disk is available for swap disk use.

```
lsblk
blkid
df -Th
```

Format the disk.

```
fdisk /dev/xvda
```

Create a swap disk.

```
sudo mkswap -f /dev/xvda
sudo swapon -s /dev/xvda
# or
sudo swapon /dev/xvda
```

Check if swap disk is available.

```
lsblk
free -h 
cat /proc/swaps
cat /proc/meminfo
swapon -s
top
vmstat
vmstat 1 5
```