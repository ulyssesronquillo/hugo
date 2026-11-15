---
title: 'testing a network port connection'
author: ulysses

date: 2018-10-10
slug: testing-a-network-port-connection
draft: false
---

You can test a network port connection using the “nc” command on Linux and “telnet” on Windows.

Format:  
$ nc -zv domain.com port  
C:\> telnet domain.com port

```
$ nc -zv domain.com 80
Connection to domain.com 80 port [tcp/http] succeeded!
```

```
C:\> telnet -zv domain.com 80
Connecting To domain.com...Could not open connection to the host, on port 80: Connect failed
```

For Telnet, if a connection is successful, it returns no message.