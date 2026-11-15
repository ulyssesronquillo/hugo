---
title: 'mysql restore to another db'
author: ulysses

date: 2020-06-14
slug: mysql-restore-to-another-db
draft: false
---

In order to restore a MySQL database to another database, use routines and triggers.

```
mysqldump -p user -p --routines --triggers db1 > db1.sql
```

To restore to another database, just use the normal command.

```
mysql -u user -p db2 
```