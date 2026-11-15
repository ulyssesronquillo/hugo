---
title: 'revised wordpress permissions'
author: ulysses

date: 2018-11-23
slug: revised-wordpress-permissions
draft: false
---

Here’s my revised WordPress permissions. Originally, I had it set to:

```
$ sudo chown -R www-data:www-data /var/www
$ find /var/www -type d -exec sudo chmod 755 {} \;
$ find /var/www -type f -exec sudo chmod 644 {} \;
```

This is a very safe setup as recommended by quite a few WordPress security gurus.

However, here’s the issue. When you try to FTP as “ulysses” user, it won’t let you overwrite files, because it doesn’t have write access to the “/var/www” directory since it’s owned by www-data. To fix the permission issue, first you have to add the “ulysses” user to the www-data group. See below. In addition, you’ll need to change ownership of the files and directories to the “ulysses” user and give “ulysses” user full access to the files. Change file permissions to 775, and directory permissions to 664.

```
$ sudo usermod -a -G www-data ulysses
$ sudo chown -R ulysses:www-data /var/www
$ find /var/www -type d -exec sudo chmod 775 {} \;
$ find /var/www -type f -exec sudo chmod 664 {} \;
```

Everything is all and good, until you try to add a plugin within the WordPress console. It’s now asking for your FTP credentials which most people don’t have setup. The simple fix here is to the following line in your wp-config.php file.

```
$ vi /var/www/html/wp-config.php
# Add the following ...
define('FS_METHOD', 'direct');
```

While you are at it, you should also change wp-config.php permissions to 660. Some people recommend 600, but then you’ll end up with the same permission issue as before, user “ulysses” will not have access to the wp-config.php file. So 660 is the preferred value.

```
$ sudo chmod 660 /var/www/html/wp-config.php
```

That should take care of everything.