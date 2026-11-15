---
title: 'yum rpmdb failed'
author: ulysses

date: 2019-10-04
slug: yum-rpmdb-failed
draft: false
---

If you are getting an error similar to the yum error below, yum may be broken in your system.

```
error: rpmdb: BDB0113 Thread/process 2196/139984719730496 failed: BDB1507 Thread died in Berkeley DB library
error: db5 error(-30973) from dbenv->failchk: BDB0087 DB_RUNRECOVERY: Fatal error, run database recovery
error: cannot open Packages index using db5 - (-30973)
error: cannot open Packages database in /var/lib/rpm
CRITICAL:yum.main:

Error: rpmdb open failed
```

Here’s the fix.

```
mv /var/lib/rpm/__db* /tmp
yum clean all
```

Run your yum commands. The errors should be gone.