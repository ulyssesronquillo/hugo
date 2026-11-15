---
title: 'install laravel 5.5 on ubuntu 16.04'
author: ulysses

date: 2017-11-28
slug: install-laravel-5-5-on-ubuntu-16-04
draft: false
---

Laravel is a MVC framework for PHP. The latest Laravel release is version 5.5 in July 2017. Laravel 5.5 requires PHP 7 and higher. The latest stable release of PHP is 7.1. The following instructions walks you through how to install Laravel 5.5 on Ubuntu 16.04 LTS.

Update

```
sudo apt-get update
sudo apt-get upgrade
```

Install Apache

```
# install apache
sudo apt-get install apache2
# start apache
sudo systemctl start apache2
# enable on startup
sudo systemctl enable apache2
```

Install PHP 7

```
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
sudo apt install php7.1 php7.1-xml php7.1-mbstring php7.1-mysql php7.1-json php7.1-curl 
sudo apt install php7.1-cli php7.1-common php7.1-mcrypt php7.1-gd libapache2-mod-php7.1 php7.1-zip
```

Install Composer

```
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/bin/composer
```

Change Permissions

```
# add new user to www-data group
sudo useradd -g www-data ubuntu
# add existing user to www-data group
sudo usermod -a -G www-data ubuntu
# change ownership
sudo chown -R ubuntu:www-data /var/www
# change permissions
sudo chmod -R g+rwx /var/www
```

Install Laravel 5.5 via Composer

```
composer create-project laravel/laravel /var/www/html/web
```

Make Storage Writeable

```
sudo chmod -R 777 /var/www/html/web/storage
```

Set Document Root in Apache

```
sudo nano /etc/apache2/sites-available/000-default.conf
# change DocumentRoot to laravel/public
DocumentRoot "/var/www/html/laravel/public"
# Save and Exit
```

Restart Apache

```
sudo systemctl restart apache2
```

There you have it. Laravel 5.5 on Ubuntu 16.04 LTS. Enjoy.