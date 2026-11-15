---
title: 'adding a xfs volume'
author: ulysses

date: 2019-03-07
slug: adding-a-xfs-volume
draft: false
---

Add a disk volume via cloud console. Then perform the following commands:

```
# check the new block
lsblk
# format
fdisk /dev/sdc
# create file system
mkfs.xfs -f /dev/sdc1
# get uuid
blkid /dev/sdc1
# vi /etc/fstab
UUID="xxxxxxxxxxxxxxxxxxxxx" /mnt/directory xfs defaults 0 0
# mount
mount -a
```