---
title: 'fix apache fdq error'
author: ulysses

date: 2013-05-12
slug: fix-apache-fdq-error
draft: false
---

If you’re working on Ubuntu and running Apache, you probably have seen this error when rebooting Apache. It says “could not reliably determine the server’s fully qualified domain name.” There’s a simple fix to this configuration issue.

You’ll need to edit the /etc/apache2/httpd.conf config file:

```
sudo nano /etc/apache2/httpd.conf
```

and add this entry:

```
ServerName localhost
```

Reboot Apache

```
sudo /etc/init.d/apache2 restart
```

The error is now gone.