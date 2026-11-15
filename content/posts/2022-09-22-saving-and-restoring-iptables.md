---
title: 'saving and restoring iptables'
author: ulysses

date: 2022-09-22
slug: saving-and-restoring-iptables
draft: false
---

iptables can be saved or loaded from a file. Here’s a way to do it.

Saving to a file

```
# Debian/Ubuntu
iptables-save > /etc/iptables/rules.v4
# Redhat/Centos/Rocky
iptables-save > /etc/sysconfig/iptables
```

Loading from a file

```
# Debian/Ubuntu
iptables-restore > /etc/iptables/rules.v4
# Redhat/Centos/Rocky
iptables-restore > /etc/sysconfig/iptables
```

Listing rules

```
iptables -L
```