---
title: 'dropbox folder as web root'
author: ulysses

date: 2012-12-08
slug: dropbox-folder-as-web-root
draft: false
---

One of many clever ways you can do with Dropbox is to make it the web root of your development server. There’s an advantage to doing this, as I’ll explain in this post. Currently, I have Dropbox installed on my Linux Mint desktop. I also use the desktop as my web development server. I have Apache, PHP, MySQL, etc. installed. Typically the web root of the Apache web server, is located in the /var/www directory. I’ve changed mine to a Dropbox folder at /home/ulysses/Dropbox/web/.

There’s an advantage to making Dropbox the web root. I normally use multiple computers to code. I have a Linux desktop, Macbook Air, and a Windows machine. I installed Dropbox on all of them, and placed my code in a Dropbox folder to share files. My code is always synched on all computers. Each time I move to another computer, I can always access the same code, because Dropbox does a fantastic job of synching files on all my computers.

In addition, I made Dropbox the web root of my development server, so every time I make a file change, the development web server is also updated. So, there is no more need for me to FTP or copy files to my development server. One more thing, if my desktop is turned on at home, any changes I make away from home, are reflected on my development server instantaneously.

To change Apache’s web root, edit the **/etc/apache2/sites-available/default** config file. Change the default directory from /var/www to /home/ulysses/Dropbox/web/, the location of my Dropbox folder.

```
DocumentRoot /home/ulysses/Dropbox/web
<directory></directory>
 Options FollowSymLinks
 AllowOverride None
<directory></directory>
 Options Indexes FollowSymLinks Multiviews
 AllowOverride All
 Order allow,deny
 allow from all
```

Do the same for the **/etc/apache2/sites-enabled/default** config file.

Finally, restart Apache.

```
$ sudo /etc/init.d/apache2 restart
```