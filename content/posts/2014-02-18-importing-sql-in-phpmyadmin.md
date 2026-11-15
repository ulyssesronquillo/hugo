---
title: 'importing sql in phpmyadmin'
author: ulysses

date: 2014-02-18
slug: importing-sql-in-phpmyadmin
draft: false
---

If you have a problem importing SQL files into phpMyAdmin, the issue could be that the upload limit in PHP is set too low. By default, PHP sets the upload file limit to 2MB, which is too low for most people. You can increase the limit to something more realistic such as 16MB, if you’re working mostly with medium-sized SQL databases.

If you have access to the Terminal and have root access, you can edit your PHP.ini settings. First, you need to find out where your default PHP.ini is located. There might be several PHP.ini files in your system, but there’s only one bound to Apache. To determine to which one is being used, I suggest you create a file that contains the PHP function called phpinfo(). Place this file your web server and run it.

Create a file called phpinfo.php. Enter the code below. Save. Upload to server.

```
<?php phpinfo(); ??>
```

Now, open your browser and point the URL where your phpinfo.php is stored on your web server. The phpinfo.php file will run the phpinfo() function and will display the environment variables being used by Apache. Near the top of the page, you’ll see the path of the php.ini. Now that you know where your php.ini file is exactly located, you’ll need to edit that file and look for the Upload Limits.

In Ubuntu, my php.ini is located in /etc/php5/apache2/php.ini.

```
sudo nano /etc/php5/apache2/php.ini
```

Look for the File Uploads text as displayed below. Change from 2M to 16M. Save file.

```
;;;;;;;;;;;;;;;;
; File Uploads ;
;;;;;;;;;;;;;;;;

upload_max_filesize = 16M
```

Finally, you need to reboot Apache for your changes take effect.

```
sudo /etc/init.d/apache restart
```