---
title: 'install php on mac'
author: ulysses

date: 2013-12-27
slug: install-php-on-mac
draft: false
---

This article will show you how to install PHP on the Mac. By default, Apache and PHP are already installed on the Mac, although both are not activated. We must first enable Apache. Once you’ve Apache is enabled, you can then proceed in activating PHP.

> This article is part of a series of articles on how to manually install Apache, PHP, MySQL on the Mac OS. Installing the popular MAMP application is as simple as installing any other application on the Mac, but it will not give you any valuable learning experience, nor will you have complete control of your development environment. I recommend manually installing the individual applications to maximize your learning experience.

#### How to Install PHP on Mac OS X

PHP is already installed. We just have to enable it. Edit the ‘**/etc/apache2/httpd.conf**‘ file.

```
$ sudo nano /etc/apache2/httpd.conf
```

Uncomment or delete the ‘#’ sign for the line that contains the text below.

```
LoadModule php5_module libexec/apache2/libphp5.so
```

Restart Apache

```
$ sudo apachectl restart
```

Place a index.php file that contains the following in your web server root.

```
<?php phpinfo(); ??>
```

If you see PHP info and stats, that means PHP is working! If you see the code, it means PHP is not working.