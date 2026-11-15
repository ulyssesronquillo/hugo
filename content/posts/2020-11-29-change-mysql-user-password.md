---
title: 'change mysql user password'
author: ulysses

date: 2020-11-29
slug: change-mysql-user-password
draft: false
---

This is a very simple command to run. Login to MySQL first and run the following the command line.

```
ALTER USER username IDENTIFIED BY 'password';
```

Flush privileges for changes to take effect.

```
flush privileges;
```