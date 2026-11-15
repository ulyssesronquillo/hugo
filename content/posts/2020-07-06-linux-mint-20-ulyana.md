---
title: 'linux mint 20 ulyana'
author: ulysses

date: 2020-07-06
slug: linux-mint-20-ulyana
draft: false
---

I upgraded my desktop to Linux Mint 20 Ulyana over the weekend.

Edit your package repository. Replace tricia with ulyana, and bionic with focal.

```
vim /etc/apt/sources.list.d/official-package-repositories.list
```

Run update first.

```
apt update -y
apt upgrade -y
```

Perform upgrade to Linux Mint 20. When prompted, choose default.

```
apt dist-upgrade
```

Reboot.

```
reboot
```

cat /etc/os-release.

```
ulysses@penguin:~/Code$ cat /etc/os-release
NAME="Linux Mint"
VERSION="20 (Ulyana)"
ID=linuxmint
ID_LIKE=ubuntu
PRETTY_NAME="Linux Mint 20"
VERSION_ID="20"
HOME_URL="https://www.linuxmint.com/"
SUPPORT_URL="https://forums.ubuntu.com/"
BUG_REPORT_URL="http://linuxmint-troubleshooting-guide.readthedocs.io/en/latest/"
PRIVACY_POLICY_URL="https://www.linuxmint.com/"
VERSION_CODENAME=ulyana
UBUNTU_CODENAME=focal
```