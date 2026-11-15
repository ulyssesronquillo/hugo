---
author: ulysses
title: 'fixing apache errors'
date: 2024-08-04
slug: fixing-apache-errors
draft: false
---
I was getting an Apache error on startup and during a restart after upgrading to Linux Mint 22.

As it turned out, the module that's enabled is php8.1. It should be 8.3.

Here's the fix:

```
sudo a2dismod php8.1
sudo systemctl restart apache2
```

This did the trick, but I was getting another error during restarting services. 

The error says "could not reliably determin the server fully qualified domain."

Here's the fix for that.

```
sudo vi /etc/apache2/apache2.conf
```

Insert

```
ServerName localhost
```

Restart Apache

```
sudo systemctl restart apache2 
```

