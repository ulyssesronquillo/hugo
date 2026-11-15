---
title: 'change hostname amazon linux'
author: ulysses

date: 2023-06-06
slug: change-hostname-amazon-linux
draft: false
---

Here’s how to make a hostname stick on Amazon Linux.

Set preserve\_hostname to true in /etc/cloud/cloud.cfg.

```
preserve_hostname: true
```

Set the hostname in /etc/sysconfig/network.

```
HOSTNAME=server.domain.com
NETWORKING=yes
NOZEROCONF=yes
```

Reboot the server to make sure hostname sticks after a reboot.

```
shutdown -r now
```

Login to confirm hostname sticks.