---
author: ulysses
title: 'keyboard freeze'
date: 2026-02-07
slug: keyboard-freeze
draft: false
---
Another potential fix to my keyboard freezing problem on Linux Mint 22.1 after going to sleep.

Edit Grub.

```
sudo vi /etc/default/grub
```

Add i8042.dubkdbd=1 to the GRUB_CMDLINE_LINUX_DEFAULT.

```
GRUB_CMDLINE_LINUX_DEFAULT="usbcore.autosuspend=-1 quiet splash i8042.dumbkbd=1"
```

Update Grub and reboot.

```
sudo update-grub
reboot
```

Hopefully that fixes it.
