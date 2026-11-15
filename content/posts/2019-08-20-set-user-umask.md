---
title: 'set user umask'
author: ulysses

date: 2019-08-20
slug: set-user-umask
draft: false
---

How to set up umask for a Linux user.

```
# sets umask for all users
vi /etc/profile
# sets umask for a user
vi ~/.bashrc
```

Add the following umask line to the file.

```
umask 0022
```