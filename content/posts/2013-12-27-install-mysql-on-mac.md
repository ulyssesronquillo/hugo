---
title: 'install mysql on mac'
author: ulysses

date: 2013-12-27
slug: install-mysql-on-mac
draft: false
---

This article shows you how to install MySQL on the Mac OS X. MySQL is an open-source relational database management system used in majority of websites on the Internet. MySQL works on many platforms including Windows, Mac and many flavors of the Linux OS.

> This article is part of a series of articles on how to manually install Apache, PHP, MySQL on the Mac OS. Installing the popular MAMP application is as simple as installing any other application on the Mac, but it will not give you any valuable learning experience, nor will you have complete control of your development environment. I recommend manually installing the individual applications to maximize your learning experience.

#### How to Install MySQL on Mac OS X

First, download the [MySQL](http://dev.mysql.com/downloads/mysql/) dmg archive for the Mac OS.

Install the following 3 items:

1. MySQL package
2. MySQL Startup Item package
3. MySQL Preferences Pane

Add the MySQL path to your existing path so you can invoke MySQL commands from anywhere.

```
$ export PATH=/usr/local/mysql/bin:$PATH
```

Secure the database. You’ll be prompted to provide a new MySQL password.

```
$ sudo mysql_secure_installation
```

Make sure MySQL is connected to Apache and PHP.

```
cd /var 
sudo mkdir mysql 
cd mysql 
sudo ln -s /tmp/mysql.sock mysql.sock
```

Access MySQL from the Terminal. Provide your password when prompted.

```
$ mysql -u root -p
```

Once logged in, you can check the databases just to be sure you’re connected.

```
mysql> show databases;
exit;
```