---
title: 'check open ports remotely'
author: ulysses

date: 2021-08-17
slug: check-open-ports-remotely
draft: false
---

Here are a few tools to check if ports are open from a remote host.

```
nc -zvw10 192.168.0.1 22
nmap 192.168.0.1 -p 22
telnet 192.168.0.1 22
```

You may have to install netcat and nmap if missing in your distro.

```
yum install nc
yum install nmap
```