---
title: 'rpmdb open failed'
author: ulysses

date: 2021-05-22
slug: rpmdb-open-failed
draft: false
---

If you get this error, something happened to the rpm database. To fix.

```
rm -f /var/lib/rpm/__db*
db_verify /var/lib/rpm/Packages
rpm --rebuilddb
yum clean all
```

Run yum again.