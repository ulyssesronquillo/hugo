---
title: 'recover mysql root password'
author: ulysses

date: 2019-09-02
slug: recover-mysql-root-password
draft: false
---

How to recover a MySQL root password without a password.

1. Stop MySQL.
2. Start MySQL Safe Mode.
3. Login to MySQL as root without password.
4. Change root password.

```
# Stop MySQL.
service mysql stop
# MySQL Safe Mode.
mysqld_safe --skip-grant-tables &
```

```
# Login to MySQL without password. Set new password.
mysql -u root -p
use mysql;
# For MySQL 5.6 or lower
UPDATE mysql.user SET Password=PASSWORD('newpassword') WHERE User='root';
# For MySQL 5.7 or higher
SET PASSWORD FOR 'root'@'localhost' = PASSWORD("newpassword");
FLUSH PRIVILEGES;
exit;
```

```
# Kill mysqld
killall mysqld
# Restart MySQL
service mysql start
```

I ran into issues running MySQL Safe mode. I got a “UNIX socket file don’t exists” error. Here’s the fix.

```
mkdir -p /var/run/mysqld
chown mysql:mysql /var/run/mysqld
```