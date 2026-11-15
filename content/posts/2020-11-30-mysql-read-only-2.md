---
title: 'mysql read only'
author: ulysses

date: 2020-11-30
slug: mysql-read-only-2
draft: false
---

If you need to perform backup or replicate a database, you can lock up the database by doing a global read block to make it read-only.

The process is:

1. Make the server read-only, so that it processes only retrievals and blocks updates.
2. You can then perform the backup.
3. Change the server back to its normal read/write state.

Read only.

```
FLUSH TABLES WITH READ LOCK;
SET GLOBAL read_only = ON;
```

Back to normal mode.

```
SET GLOBAL read_only = OFF;
UNLOCK TABLES;
```

You can run these MySQL commands within MySQL or via a bash terminal. Check out my previous post.