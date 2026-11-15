---
title: 'check reboot after updates'
author: ulysses

date: 2021-07-16
slug: check-reboot-after-updates
draft: false
---

Here’s the command to check if the system needs a reboot after running yum update.

Must be root or run it sudo.

```
$ needs-restarting -r ; echo $?
Core libraries or services have been updated:
  openssl-libs -> 1:1.0.2k-21.el7_9
  kernel -> 3.10.0-1160.31.1.el7
  dbus -> 1:1.10.24-15.el7
  linux-firmware -> 20200421-80.git78c0348.el7_9
  glibc -> 2.17-324.el7_9
  systemd -> 219-78.el7_9.3

Reboot is required to ensure that your system benefits from these updates.

More information:
https://access.redhat.com/solutions/27943
1
```

In this instance, it requires a reboot due to a new kernel.