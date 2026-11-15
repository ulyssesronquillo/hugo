---
title: 'sudoers directory'
author: ulysses

date: 2019-04-08
slug: sudoers-directory
draft: false
---

What’s in the /etc/sudoers.d/ directory? It’s a group of files with the following format as displayed in the code below. In the example, the file allows a Linux group or an AD group to assume the role of root, via the sudo command. As long as the group uses the correct format, and is located inside the /etc/sudoers.d/ directory, that group will have access to root.

```
%groupname  ALL=(ALL)   NOPASSWD: ALL
```