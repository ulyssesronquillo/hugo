---
title: 'powershell test network connection'
author: ulysses

date: 2020-06-15
slug: powershell-test-network-connection
draft: false
---

Here’s the command to test a network connection in Powershell.

```
C:> Test-NetConnection -ComputerName server -Port 443
```

Result:

```
ComputerName     : server
RemoteAddress    : 10.0.0.5
RemotePort       : 443
InterfaceAlias   : Ethernet 0
SourceAddress    : 10.1.1.34
TcpTestSucceeded : True
```