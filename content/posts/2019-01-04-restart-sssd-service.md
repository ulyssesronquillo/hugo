---
title: 'restart sssd service'
author: ulysses

date: 2019-01-04
slug: restart-sssd-service
draft: false
---

Just documenting how to restart SSSD service. SSSD is a service that allows Active Directory groups access to Linux systems.

```
systemctl restart sssd.service
```

For other or older Linux distros, you may have to use this:

```
service sssd restart
```

You can always try the other if one doesn’t work.