---
title: 'change mysql password'
author: ulysses

date: 2015-10-08
slug: change-mysql-password
draft: false
---

The following are instructions on how to change your MySQL password from the Unix command line.

Login to MySQL and access MySQL table.

```
mysql -u root -p
use mysql;
```

Change the password for any user, flush privileges and quit.

```
update user set password=PASSWORD('new_password') where User='root';
flush privileges;
quit
```

Make sure to make password changes on your applications as well.

In WordPress, edit the wp-config.php file to change database password.