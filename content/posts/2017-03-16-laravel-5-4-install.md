---
title: 'laravel 5.4 install'
author: ulysses

date: 2017-03-16
slug: laravel-5-4-install
draft: false
---

This is the installation of Laravel 5.4 on an Ubuntu Server 16.04 LTS. Laravel requires that you run Apache, MySQL and PHP. In this installation, I’m using the following versions: Apache 2.4.18, MySQL 5.7.17 and PHP 7.0.15. The installation of Laravel has changed over the years. I wished the installation was simpler. You can try Forge, but it’s not free. It also requires that you have an account at Linode, Digital Ocean or AWS. Forge costs $15 per month and Forge Plus is $30 per month. If you don’t want to pay, I’m afraid you are going to have to install Laravel yourself. Laravel installation may vary based on the distro you’re using. These instructions are for the Ubuntu Server 16.04 LTS.

Run Update

```
sudo apt-get update
sudo apt-get upgrade
```

Install Apache

```
sudo apt-get install apache2
sudo a2enmod rewrite
sudo service apache2 restart
```

Install MySQL

```
sudo apt-get install mysql-server
sudo mysql_secure_installation
```

Install PHP

```
sudo apt-get install php libapache2-mod-php php-mbstring php-zip php-xml php-mysql
```

Install Composer

```
sudo curl -sS https://getcomposer.org/installer | sudo php — —install-dir=/usr/local/bin —filename=composer
# you may have to move composer manually if it doesn't work
sudo mv composer.phar /usr/local/bin/composer
# check if composer is accessible globally
composer -V
```

Install Laravel Installer

```
composer global require "laravel/installer"
# Using alias instead of $PATH
echo 'alias laravel="~/.composer/vendor/bin/laravel"' >> ~/.bashrc
source ~/.bashrc
# add source ~/.bashrc to .profile to load automatically
echo 'source ~/.bashrc' >> ~/.profile
# restart apache
sudo service apache2 restart
# check if laravel is accessible globally
laravel
```

Install New Laravel Project

```
# set permissions
cd /var/www/
sudo chown -R ubuntu:ubuntu /var/www/html
sudo chmod -R 755 /var/www/html
# install new project
cd /var/www/html
laravel new project
# give apache permissions 
sudo chgrp -R www-data /var/www/html/project/storage
sudo chgrp -R www-data /var/www/html/project/bootstrap/cache
```

Configure Apache

```
cd /etc/apache2/sites-available
sudo cp 000-default.conf project.conf
sudo nano project.conf
#
<virtualhost>
  ServerName local.project.com
  ServerAdmin admin@project.com
  DocumentRoot /var/www/html/project/public
  <directory>
    AllowOverride All
  </directory>
  ErrorLog ${APACHE_LOG_DIR}/error.log
  CustomLog ${APACHE_LOG_DIR}/access.log combined
</virtualhost>
#
sudo a2ensite project.conf
sudo a2dissite 000-default.conf
sudo service apache2 restart
```

Finally, you can now access Laravel from the browser from the server IP address or domain.