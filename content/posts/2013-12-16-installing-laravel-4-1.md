---
title: 'installing laravel 4.1'
author: ulysses

date: 2013-12-16
slug: installing-laravel-4-1
draft: false
---

[Laravel](http://laravel.com) version 4.1 was released just a couple of days ago. With the latest release of Laravel, the installation and setup couldn’t be any easier. In this article, I will show you how easy it is to install Laravel on [Ubuntu](http://ubuntu.com). You can quickly adapt these commands to other Linux flavors using either the ‘yum’ or ‘rpm’ commands.

The preferred way of installing Laravel is by using [Composer](http://getcomposer.org/), which is a dependency manager for PHP. In this article, I will be using Composer because it’s by far the easiest way to install Laravel.

First things first, update Ubuntu to the latest and greatest patches.

```
$ sudo apt-get update
$ sudo apt-get upgrade
```

You can skip the following command if you’ve already installed Apache, MySQL and PHP.

```
$ sudo apt-get install apache2 mysql-server mysql-client php5 libapache2-mod-php5
```

In addition, we also want to make sure PHP5 mcrypt and Json is also installed.

```
$ sudo apt-get install php5-mcrypt php5-common
```

We will now install Composer first using the curl command from the Terminal. Once the install is finished, we will now rename ‘composer.phar’ to ‘composer’ and move it to the ‘/usr/local/bin’ directory so it’s accessible from anywhere on the system.

```
$ curl -sS https://getcomposer.org/installer | php
$ sudo mv composer.phar /usr/local/bin/composer
```

Now that we have Composer installed, we will now install Laravel using Composer. The only variable that we need to modify is ‘test.’ This is the target directory where Laravel will be installed from the current directory.

```
$ composer create-project laravel/laravel test --prefer-dist
```

Relax and grab a cup of coffee. This process will take approximately 2-3 minutes to complete. Composer will be installing Laravel and all its dependencies.

After Laravel install is complete, we need to give read and write permissions to the app/storage directory.

```
$ sudo chmod 777 app/storage
```

You can now access Laravel from the browser. To make it simpler, you can setup a virtual host if you like. I recently wrote an article on how to create a [new virtual host](http://uly.me/virtual-apache-host/). Check it out.