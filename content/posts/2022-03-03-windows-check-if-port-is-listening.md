---
title: 'windows check if port is listening'
author: ulysses

date: 2022-03-03
slug: windows-check-if-port-is-listening
draft: false
---

Here’s how to check if port is listening on a Windows Server.

Log in to the destination server.

```
netstat -ano | find "443" | find "LISTEN"
tasklist /fi "PID eq "443"
```