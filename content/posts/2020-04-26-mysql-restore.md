---
title: 'mysql restore'
author: ulysses

date: 2020-04-26
slug: mysql-restore
draft: false
---

Here’s how to restore a MySQL database from mysqldump.

```
mysql -u user -p
mysql> drop database databasename;
mysql> quit;
Bye
mysql -u user -p databasename 
```

Drop database first, then import the SQL file.