---
title: 'redhat 8 network manager'
author: ulysses

date: 2022-03-10
slug: redhat-8-network-manager
draft: false
---

In Redhat 8, every time you the Network Manager get’s restarted it overwrites /etc/resolv.conf. To prevent that from hapenning, create a new file called /etc/NetworkManager/conf.d/90-dns-none.conf and add the following lines. Restart Network Manager. Your /etc/resolv.conf should be unchanged.

```
[main]
dns=none
```

Restart Network Manager

```
$ systemctl reload NetworkManager
```