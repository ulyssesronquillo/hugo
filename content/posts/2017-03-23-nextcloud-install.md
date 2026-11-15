---
title: 'nextcloud install'
author: ulysses

date: 2017-03-23
slug: nextcloud-install
draft: false
---

NextCloud is an open-source next-generation file sharing and file synching web-application that you can run and install on your own Linux server. It’s similar to Dropbox, the file-sharing cloud application. The big difference between Dropbox and NextCloud is that you get to run your own cloud storage on your own server. The following are instructions on how to install NextCloud on an Ubuntu Server 16.04 LTS server.

Run Updates First

```
$ sudo apt-get update
$ sudo apt-get upgrade -y
$ sudo apt-get dist-upgrade -y
```

Install Apache

```
$ sudo apt-get install apache2
```

Install MySQL Server

```
$ sudo apt-get install mysql-server mysql-client
$ sudo mysql_secure_installation
```

Install PHP

```
$ sudo apt-get install php libapache2-mod-php php-mbstring php-zip php-xml php-mysql php-gd
$ sudo apt-get install php-json php-curl php-intl php-mcrypt php-imagick php-dom unzip
```

Edit php.ini change the memory limit and upload and post file sizes to something bigger. Restart Apache.

```
$ sudo nano /etc/php/7.0/apache2/php.ini
memory_limit = 512M
upload_max_filesize = 500M
post_max_size = 500M
$ sudo service apache2 restart
```

Create Database and User. Flush privileges.

```
$ mysql -u root -p
mysql> create database nextcloud;
mysql> grant all privileges on nextcloud.* to 'ncuser'@'localhost' identified by 'password';
mysql> flush privileges;
mysql> exit;
```

Download and Install the latest Nextcloud. Give permissions to Apache.

```
$ cd /var/www/html
$ sudo wget https://download.nextcloud.com/server/releases/nextcloud-11.0.2.zip
$ sudo unzip nextcloud-11.0.2.zip
$ sudo chown -R www-data:www-data nextcloud
```

Setup Apache

```
$ sudo nano /etc/apache2/sites-available/nextcloud.conf

Alias / "/var/www/html/nextcloud/"

 Options +FollowSymlinks
 AllowOverride All
 
  Dav Off
 
 SetEnv HOME /var/www/html/nextcloud
 SetEnv HTTP_HOME /var/www/html/nextcloud


```

Enable Nextcloud. Disable default.

```
$ sudo a2ensite nextcloud.conf
$ sudo a2dissite 000-default.conf
```

Enable the following

```
$ sudo a2enmod rewrite
$ sudo a2enmod headers
$ sudo a2enmod env
$ sudo a2enmod dir
$ sudo a2enmod mime
$ sudo service apache2 restart
```

Open your browser and access your server via IP address or domain name to complete the NextCloud install.

You will be asked to enter a new username and password. Also enter your database credentials to complete the installation.