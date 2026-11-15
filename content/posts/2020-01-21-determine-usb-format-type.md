---
title: 'determine usb format type'
author: ulysses

date: 2020-01-21
slug: determine-usb-format-type
draft: false
---

Here’s how to determine what type of USB format a thumb drive is in Linux.

- df -Th (shows the file system type)
- lsblk (shows the block devices)
- lsusb (show usb ports and devices)
- fdisk -l (displays the USB format type)

To display, use “fdisk -l” to display either NTFS, FAT32 or exFAT32.