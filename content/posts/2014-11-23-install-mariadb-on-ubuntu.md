---
title: 'install mariadb on ubuntu'
author: ulysses

date: 2014-11-23
slug: install-mariadb-on-ubuntu
draft: false
---

MariaDB is a drop-in replacement for MySQL database. On most cases, you can just uninstall MySQL and install MariaDB and you are good to go. To keep up the two databases compatible, the MariaDB team are doing monthly merges with the MySQL code base making sure new features and fixes are kept up.

Uninstall MySQL

```
sudo apt-get purge mysql*
sudo apt-get autoremove
```

Install MariaDB

```
sudo apt-get install mariadb-server mariadb-client -y
```

Verify if MariaDB is running

```
sudo service mysql status
```