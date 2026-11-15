---
title: 'install phpmyadmin on mac'
author: ulysses

date: 2013-12-27
slug: install-phpmyadmin-on-mac
draft: false
---

This article covers how to install PhpMyAdmin on Mac OS X. PhpMyAdmin is a software tool written in PHP to manage and administer MySQL databases. It supports not only MySQL, but also MariaDB and Drizzle databases. PhpMyAdmin supports a variety of database operations such as managing databases, tables, columns, relations, indexes, users, and permissions.

> This article is part of a series of articles on how to manually install Apache, PHP, MySQL on the Mac OS. Installing the popular MAMP application is as simple as installing any other application on the Mac, but it will not give you any valuable learning experience, nor will you have complete control of your development environment. I recommend manually installing the individual applications to maximize your learning experience.

#### How to Install PhpMyAdmin on Mac OS X

To install PhpMyAdmin, download the latest [version](http://phpmyadmin.net).

Unzip the file and rename the folder to ‘**phpmyadmin**.’

Move the ‘phpmyadmin’ folder to ‘**/usr/local/phpmyadmin**.’

```
$ sudo mv phpmyadmin /usr/local/phpmyadmin
```

Copy the config.sample.inc.php to config.inc.php.

```
$ cd /usr/local/phpmyadmin
$ sudo cp config.sample.inc.php config.inc.php
```

Create a config file in ‘**/etc/apache2/other**.’

```
$ sudo touch /etc/apache2/other/phpmyadmin.conf
```

Edit the config file.

```
$ sudo nano /etc/apache2/other/phpmyadmin.conf
```

Add the following:

```
Alias /phpmyadmin /usr/local/phpmyadmin
<directory>
    Options Indexes
    Order allow,deny
    Allow from all
</directory>
```

Restart Apache

```
$ sudo apachectl restart
```

Finally, access PhpMyAdmin from your browser. Example: http://localhost/phpmyadmin