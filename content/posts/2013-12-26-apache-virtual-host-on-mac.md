---
title: 'apache virtual host on mac'
author: ulysses

date: 2013-12-26
slug: apache-virtual-host-on-mac
draft: false
---

Creating an Apache virtual host on your Mac is quite easy. Assuming you already have Apache installed and running on your Mac, you will now have to decide whether to serve your pages from the default web root, or create your own virtual host, and serve your pages from an alternate location.

> This article is part of a series of articles on how to manually install MAMP or Apache, PHP, MySQL on the Mac OS. Installing the popular MAMP application is as simple as installing any other application on the Mac, but it will not give you any valuable learning experience, nor will you have complete control of your development environment. I recommend manually installing the individual applications to maximize your learning experience.

#### Create an Apache Virtual Host on Mac OS X

Edit the **/etc/apache2/httpd.conf** file using the nano editor.

```
$ sudo nano /etc/apache2/httpd.conf
```

Look for the text ‘# Virtual hosts’ located at the end of the file. Uncomment by removing # from the line that says:

```
Include /private/etc/apache2/extra/httpd-vhosts.conf
```

Save file and exit. If your not familiar with nano, it’s Ctrl-O for save, and Ctrl-X for exit.

Now edit the https-vhosts.conf file.

```
$ sudo nano /private/etc/apache2/extra/httpd-vhosts.conf
```

Append the following at the end of the file:

```
<virtualhost>
	DocumentRoot "/Users/Ulysses/Sites/"
	ServerName ulysses.dev
	ErrorLog "/private/var/log/apache2/ulysses.dev.local-error_log"
	CustomLog "/private/var/log/apache2/ulysses.dev.local-access_log" common
	<directory>
		AllowOverride All
		Order allow,deny
		Allow from all
	</directory>
</virtualhost>
```

In this example, I am using an alternate web root located at ‘**/Users/Ulysses/Sites/**.’ In addition, I’m also using a made-up domain called ‘**ulysses.dev**.’ I used .dev because it’s not a real top level domain or TLD. There won’t be a conflict with a real existing domain on the Internet. You can use any domain or TLD that you like.

The final step. Edit your hosts file to add your domain. This step is very important since we are using a made-up domain that doesn’t exist. By editing our hosts file, we are spoofing our system that a host does exist.

```
$ nano /private/etc/hosts
```

Add the following domain at the end of the line. 127.0.0.1 is the loopback address of your system.

```
127.0.0.1  ulysses.dev
```

Save file and exit.

Restart Apache

```
$ sudo apachectl restart
```

From the terminal ping your domain.

```
$ ping ulysses.dev
```

Write permissions

The Apache user on the Mac is \_www and is part of the staff group. To make the Sites folder writeable to the Apache \_www user, perform the following commands from the Terminal.

```
cd /Users/Ulysses
$ sudo chown -R _www:staff Sites
$ sudo chmod -R 755 Sites
```

Finally, open up your browser and access your domain. In this example, http://ulysses.dev.