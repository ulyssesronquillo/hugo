---
title: 'check open ports'
author: ulysses

date: 2016-11-09
slug: check-open-ports
draft: false
---

If you’re running a Linux server, here’s one way of checking as to which ports are open to the public. You can use netstat for that purpose. Netstat is a command-line network utility tool that displays network connections for tcp, routing tables, and a number of network interfaces. It’s available on Linux, MacOS and Windows.

In Linux and MacOS, type the following via the Terminal.

```
netstat -tupln
#
# -l = only services which are listening on some port
# -n = show port number, don't try to resolve the service name
# -t = tcp ports
# -u = udp ports
# -p = name of the program
#
```

If you’re in Windows, open up Powershell and type in:

```
netstat -ano | find "LISTENING"
# or
netstat -o 5
```

Don’t be surprised as to what your computer is doing.