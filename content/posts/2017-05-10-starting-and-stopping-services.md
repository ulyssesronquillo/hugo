---
title: 'starting and stopping services'
author: ulysses

date: 2017-05-10
slug: starting-and-stopping-services
draft: false
---

Linux is quite stable, but there are times that you may have to restart an application or a service after a configuration change. For the change to take effect, a restart of a service is required. The good news is starting and stopping services in Linux are quite easy.

The old way.

```
# Starting and stopping MySQL
$ sudo /etc/init.d/mysql start
$ sudo /etc/init.d/mysql stop
$ sudo /etc/init.d/mysql restart
# Starting and stopping Apache
$ sudo /etc/init.d/apache2 start
$ sudo /etc/init.d/apache2 stop
$ sudo /etc/init.d/apache2 restart
# Starting and stopping the network
$ sudo /etc/init.d/networking start
$ sudo /etc/init.d/networking stop
$ sudo /etc/init.d/networking restart
```

Via service for Debian|Ubuntu distros

```
# Starting and stopping MySQL
$ sudo service mysql start
$ sudo service mysql stop
$ sudo service mysql restart
# Starting and stopping Apache
$ sudo service apache2 start
$ sudo service apache2 stop
$ sudo service apache2 restart
# Starting and stopping the network
$ sudo service networking start
$ sudo service networking stop
$ sudo service networking restart
```

Via Systemctl for CentOS|Redhat distros

```
# Starting and stopping MySQL
$ sudo systemctl start mysqld
$ sudo systemctl stop mysqld
$ sudo systemctl restart mysqld
# Starting and stopping Apache
$ sudo systemctl start httpd
$ sudo systemctl stop httpd
$ sudo systemctl restart httpd
# Starting and stopping the network
$ sudo systemctl start network
$ sudo systemctl stop network
$ sudo systemctl restart network
```