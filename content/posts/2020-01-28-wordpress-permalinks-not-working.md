---
title: 'wordpress permalinks not working'
author: ulysses

date: 2020-01-28
slug: wordpress-permalinks-not-working
draft: false
---

Here’s a couple of things you can do to check if WordPress permalinks is not working.

1. Make sure .htaccess has the right permissions.
2. Make sure a2enmod Apache module is enabled.
3. Restart the Apache server.

```
chmod 664 /var/www/domain.com/.htaccess
a2enmod rewrite
systemctl restart apache2
```