---
title: 'ubuntu 20.04 lts lamp server'
author: ulysses

date: 2020-11-10
slug: ubuntu-20-04-lts-lamp-server
draft: false
---

Here’s how to install a LAMP server on the latest Ubuntu 20.04 LTS.

Install Apache.

```
apt install apache2
systemctl status apache2
systemctl is-enabled apache2
```

Install MariaDB.

```
apt install mariadb-server mariadb-client
systemctl status mariadb
systemctl is-enabled mariadb
mysql_secure_installation
```

Install PHP.

```
apt install php libapache2-mod-php php-mysql
systemctl restart apache2
```

Enable ssl and mod\_rewrite.

```
a2enmod ssl
a2enmod rewrite
systemctl restart apache2
```