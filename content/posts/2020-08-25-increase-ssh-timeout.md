---
title: 'increase ssh timeout'
author: ulysses

date: 2020-08-25
slug: increase-ssh-timeout
draft: false
---

Here’s how to keep your SSH timeout alive for a longer period.

Edit /etc/ssh/sshd\_config. Adjust interval and count max.

```
ClientAliveInterval 1200
ClientAliveCountMax 3
```

ClientAliveInterval is set to 1200 and ClientAliveCountMax is set to the default which is 3. This means unresponsive SSH clients will be disconnected after approximately 3600 seconds or 1 hour.