---
title: 'passive ftp firewall'
author: ulysses

date: 2019-11-18
slug: passive-ftp-firewall
draft: false
---

Passive FTP is a FTP mode that alleviates the issues with client firewalls. The client initiates a call to the server. The return traffic is allowed as long as the client has initiated it. In addition, the server sends a port command along with an ephemeral port that the client can connect to. The client initiates a call on that ephemeral port, and the connection is then established.

Egress port 21 and ephemeral ports 1024-65535 needs to be opened from the client side.

```
# From the client side, egress port 21 must be open.
tcp:21
# From the client side, ephemeral ports from port 1024 to 165535 must be open.
tcp:1024-165535
```