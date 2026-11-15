---
title: 'enable mod rewrite in ubuntu'
author: ulysses

date: 2014-08-08
slug: enable-mod-rewrite-in-ubuntu
draft: false
---

Another issue when installing Laravel on the Ubuntu server is to make sure you have the mod\_rewrite module enabled. You can turn it on by invoking the following command.

```
sudo a2enmod rewrite
sudo service apache2 reload
```

Once you’ve enabled mod_rewrite, you need to restart Apache. That should fix any of the route issues that you may have. If mod\_rewrite is disabled, you usually get 404 errors or file not found. The Laravel routes simply doesn’t work.