---
title: 'upgrade to ubuntu 20.04 lts'
author: ulysses

date: 2020-04-26
slug: upgrade-to-ubuntu-20-04-lts
draft: false
---

Now that Ubuntu 20.04 LTS (Long Term Support) is out, here’s a quick guide to upgrade to Ubuntu 20.04 LTS. You can ONLY upgrade from either Ubuntu 18.04 LTS or 19.10. If you have older versions of Ubuntu, it may not work. I suggest you back up your VM before running the upgrade, so you can quicky recover if something goes awry. This upgrade process will require sudo access.

```
# login as root
sudo -i
# check your current version
lsb_release -a
# update packages
apt update -y
apt upgrade -y
# reboot server
reboot
# remove old kernels
apt --purge autoremove
# install update manager core
apt install update-manager-core
# finally, perform the upgrade
do-release-upgrade -d
# reboot the server
reboot
# after reboot confirm
lsb_release -a
```