---
title: 'password protect phpmyadmin'
author: ulysses

date: 2016-09-09
slug: password-protect-phpmyadmin
draft: false
---

phpMyAdmin is an open-source MySQL database administration application written in PHP. The software allows database administrators, web administrators, application programmers to perform several database functions via the browser. Functions such as browse and drop databases and tables, views fields and indexes, create, copy, drop, rename and alter databases, tables, fields and indexes, perform queries, update and delete, to name just a few.

Since phpMyAdmin has direct access to your database, it needs to be secure. By default, phpMyAdmin is secured using it’s built-in login feature. If you like to make it even more secure, you can add .htaccess password protection to it by simply adding .htaccess file to the phpmyadmin pages and creating username and password file to go along with it. The following instructions will show you how to add .htaccess protection to phpMyAdmin.

Edit the phpMyAdmin Apache conf file.

```
sudo nano /etc/phpmyadmin/apache.conf
```

Add the following in the /usr/share/phpmyadmin directory section.

```
<directory>
  <ifmodule mod_authn_file.c="">
  AuthType Basic
  AuthName "phpMyAdmin"
  AuthUserFile /etc/phpmyadmin/htpasswd.protect
  </ifmodule>
  Require valid-user
</directory>
```

Make sure the htpasswd file is not accessible from the web.

Create the htpasswd file. You’ll be asked to enter the password twice.

```
sudo htpasswd -c /etc/phpmyadmin/htpasswd.protect username
```

Finally, to make sure your changes are in effect, reboot Apache.

```
sudo service apache2 restart
```