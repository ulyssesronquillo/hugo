---
title: 'linux format usb drive'
author: ulysses

date: 2020-07-09
slug: linux-format-usb-drive
draft: false
---

Here’s how to format a USB drive on Linux.

Plug in the USB drive to see mount point.

```
# scan for all drives
df -Th
Filesystem     Type     Size  Used Avail Use% Mounted on
/dev/sdc1      fuseblk   30G   66M   30G   1% /media/ulysses/451B99AF225B48EC
```

Unmount USB drive.

```
umount /dev/sdc1
```

Choose a file system type and run the appropriate format command.

```
# nfts format
mkfs.ntfs /dev/sdc1
# vfat format
mkfs.vfat /dev/sdc1
# ext4 format
mkfs.ext4 /dev/sdc1
```