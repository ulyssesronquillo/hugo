---
title: 'change mtu size'
author: ulysses

date: 2019-11-26
slug: change-mtu-size
draft: false
---

MTU means maximum transmission unit. The default value is 1500 for Ethernet, which is also the standard for the Internet. If your application or network requires a different MTU size, you can set the MTU size by running the following commands.

```
# Edit ifcfg-eth0
vi /etc/sysconfig/network-scripts/ifcfg-eth0

#Add MTU, settings:
MTU="1460"

# Save and close the file. Restart networking:
service network restart
```