---
title: 'lvm extend physical volume'
author: ulysses

date: 2019-03-14
slug: lvm-extend-physical-volume
draft: false
---

The following are instructions on how to extend a disk volume with LVM.

```
# aws cli extend volume
aws ec2 modify-volume --region us-east-1 \
--volume-id vol-xxxxxxxxxxxx --size 15 \
--volume-type gp2
# check volumes before
lsblk
# extend via growpart
growpart /dev/xvdf 1
# check volumes after
lsblk
# resize physical volume
pvresize /dev/xvdf1
# check physical volume
pvscan
# extend logical volume
lvresize -l +100%FREE /dev/data/data
# check logical volume
lvscan
# check mounts
df -Th
# resize file system
resize2fs /dev/data/data
# or
xfs_growfs /dev/mapper/root
xfs_growfs /dev/xvda1
# check mounts again for new size
df -Th
```