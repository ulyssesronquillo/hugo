---
title: 'chroot a boot disk'
author: ulysses

date: 2019-08-19
slug: chroot-a-boot-disk
draft: false
---

Here’s a quick way to chroot another boot disk. Attach the rescued boot disk first. Run lsblk and mount.

```
lsblk
mount -t xfs -o nouuid /dev/xvdf2 /mnt
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
mount --bind /dev /mnt/dev
chroot /mnt
cd /mnt
exit
```

Unmount when done.

```
umount /mnt/proc
umount /mnt/dev
umount /mnt/sys
umount /mnt
```