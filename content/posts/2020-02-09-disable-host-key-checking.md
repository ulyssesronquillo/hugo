---
title: 'disable host key checking'
author: ulysses

date: 2020-02-09
slug: disable-host-key-checking
draft: false
---

How to suppress typing “yes” when prompted by ssh.

```
#!/bin/bash
ssh-keygen -f "/home/user/.ssh/known_hosts" -R "yourdomain.com" 
ssh -o "StrictHostKeyChecking=no" -i "keys/key.pem" ubuntu@domain.com
```

1. First remove old keys in the know\_hosts file.
2. Use “StrictHostKeyChecking” to suppress prompt.