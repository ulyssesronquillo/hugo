---
title: 'sssd issues redhat 7'
author: ulysses

date: 2019-07-25
slug: sssd-issues-redhat-7
draft: false
---

Some cache to clear.

```
service sssd stop
rm -r /var/lib/sss/db/*
rm -r /var/lib/sss/mc/*
service sssd start
```

Rejoin domain. Run sssd script. Restart sssd.