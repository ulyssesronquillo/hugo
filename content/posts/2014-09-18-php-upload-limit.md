---
title: 'php upload limit'
author: ulysses

date: 2014-09-18
slug: php-upload-limit
draft: false
---

I was working on PHPMyAdmin today trying to create a copy of a database. The SQL file was bigger than 8MB. Before I uploaded, I saw a message on the page of PHPMyAdmin saying the upload limit is 8MB. All indication points to increasing the upload size in the PHP configuration.

Since my server runs on Ubuntu, the php.ini file is located in /etc/php/apache2/php.ini. You’ll need to change the following settings:

```
sudo nano /etc/php/apache2/php.ini
```

```
# Edit the following entries to file size you want
upload_max_filesize = 32M
post_max_size = 32M
```

It makes sense to match the two values because they go hand-in-hand.

The changes won’t take effect until you restart Apache.

```
sudo service apache2 restart
```