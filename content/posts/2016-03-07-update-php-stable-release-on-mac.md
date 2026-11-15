---
title: 'update php stable release on mac'
author: ulysses

date: 2016-03-07
slug: update-php-stable-release-on-mac
draft: false
---

PHP is installed by default on all Macs since OS X version 10.0.0. You can install and use MAMP, but if you prefer to use the pre-loaded version of PHP, then you may need to update it to the latest stable release. Fortunately, there’s a binary package out there that will simplify your life.

If you like to install PHP 5.6 stable release, all you need to do is run the following from the command line:

```
curl -s http://php-osx.liip.ch/install.sh | bash -s 5.6
```

If you feel adventurous, you can try PHP 7 stable release.

```
curl -s http://php-osx.liip.ch/install.sh | bash -s 7.0
```

The installer packager will ask you for your password. PHP will be installed in /usr/local/php5.

Edit your .profile and include the PATH of the new PHP version.

```
nano ~/.profile
```

Insert the following:

```
export PATH=/usr/local/php5/bin:$PATH
```

To be sure your using the new version, check the PHP version:

```
php -v 
```

You should see something similar to this:

```
PHP 5.6.19 (cli) (built: Mar  4 2016 22:35:42) 
Copyright (c) 1997-2016 The PHP Group
Zend Engine v2.6.0, Copyright (c) 1998-2016 Zend Technologies
    with Zend OPcache v7.0.6-dev, Copyright (c) 1999-2016, by Zend Technologies
    with Xdebug v2.2.5, Copyright (c) 2002-2014, by Derick Rethans
```

You now have the latest PHP 5.6 stable release.