---
title: 'mysql read only'
author: ulysses

date: 2020-11-22
slug: mysql-read-only
draft: false
---

Here’s how to make a MySQL database read only.

```
mysql> FLUSH TABLES WITH READ LOCK;
mysql> SET GLOBAL read_only = ON;
```

It’s very useful if creating a replica database.