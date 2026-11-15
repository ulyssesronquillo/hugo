---
title: 'extend linux boot'
author: ulysses

date: 2019-02-06
slug: extend-linux-boot
draft: false
---

The following commands will extend Linux Boot drive without a reboot.

List block devices. Check disk sizes.

```
lsblk
df -h
```

Determine file system type: xfs, ext2, ext3 or ext4.

```
file -s /dev/xvda1
# or
df -Th
```

Extend volume from the console or command line.

```
aws ec2 modify-volume --region us-east-1 \
--volume-id vol-xxxxxxxxxxxx --size 10 \
--volume-type gp2
```

Resize Linux partition.

```
# for /dev/xvda1
growpart /dev/xvda 1
# for /dev/xvda2
growpart /dev/xvda 2
# for ext2, ext3, ext4
resize2fs /dev/xvda1
# for xfs 
xfs_growfs /dev/mapper/root
xfs_growfs /dev/xvda1
```

Check if new file size is being displayed.

```
lsblk
df -Th
```