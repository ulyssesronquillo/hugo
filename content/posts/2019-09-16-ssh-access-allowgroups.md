---
title: 'ssh access allowgroups'
author: ulysses

date: 2019-09-16
slug: ssh-access-allowgroups
draft: false
---

If unable to login via SSH, check the /etc/ssh/sshd\_config for AllowGroups.

```
AllowGroups root groupname
```

It’s case sensitive.