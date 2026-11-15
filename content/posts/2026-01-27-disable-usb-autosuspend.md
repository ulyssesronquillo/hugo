---
author: ulysses
title: 'disable usb autosuspend'
date: 2026-01-27
slug: disable-usb-autosuspend
draft: false
---
I use a single keyboard between 2 computer systems (MacOS and Linux). I disconnect my USB keyboard on one system and plug it to another whenever I switch computers. When my keyboard is disconnected from Linux for a very long time, the system no longer recognizes the keyboard when I plugged it back in unless I reboot the system. After a little bit of a research, I found a potential solution to the issue. Essentially the fix is to disable the USB autosuspend option which will need to be added to grub. 

Here are the steps:

```
sudo sed -i 's/GRUB_CMDLINE_LINUX_DEFAULT="/&usbcore.autosuspend=-1 /' /etc/default/grub
sudo update-grub
sudo systemctl reboot
```

Hopefully it fixes the issue.
