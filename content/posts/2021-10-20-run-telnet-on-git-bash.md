---
title: 'run telnet on git bash'
author: ulysses

date: 2021-10-20
slug: run-telnet-on-git-bash
draft: false
---

Although telnet is not used regularly since insecure, it’s a handy tool for testing ports.

For example, to check if a port 80 is open, you run this command.

```
$ telnet servername 80
```

Git Bash does not come with telnet, but you can use the Windows version by using winpty.

```
$ winpty telnet servername 457
Connecting To servername...Could not open connection to the host, on port 457: Connect failed
```

If port is open, you get an empty reply, just like in Windows.