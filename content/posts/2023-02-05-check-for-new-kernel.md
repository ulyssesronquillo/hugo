---
title: 'check for new kernel'
author: ulysses

date: 2023-02-05
slug: check-for-new-kernel
draft: false
---

Checking for new kernel on multiple distros.

Redhat, Centos, Fedora, Rocky

```
rpm -qa kernel
yum list installed kernel
```

Arch Linux

```
pacman -Q | grep linux
```

Fedora

```
dnf list installed kernel
```

SUSE

```
rpm -qa | grep -i kernel
zypper search -i kernel
```

Debian, Ubuntu, Mint

```
dpkg --list | grep linux-image
```