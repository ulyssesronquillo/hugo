---
title: 'exfat compatibility'
author: ulysses

date: 2017-08-07
slug: exfat-compatibility
draft: false
---

When formatting thumb drives, Windows give you the flexibility to choose which format to use, whether it’s NTFS, FAT32, and exFAT. Windows will support all three formats. There are advantages and disadvantages to each format. I’m not going to cover in detail the differences between all three. You can read them [here](https://www.howtogeek.com/235596/whats-the-difference-between-fat32-exfat-and-ntfs/). Here is where it makes sense though. If you need full compatibility, especially if you’re switching between Windows and Mac, then I recommend that you use the exFAT format. It’s readable and writeable on both Windows and MacOS. The only downside is Linux. For full compatibility, you need to install a couple of packages called exfat-fuse and exfat-utils in your Linux distro. You can use this [guide](https://www.howtogeek.com/235655/how-to-mount-and-use-an-exfat-drive-on-linux/). Hopefully, this short article and the linked articles, benefits you, in terms of choosing the correct format that’s best for your needs.