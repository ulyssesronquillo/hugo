---
title: 'fix wordpress permissions'
author: ulysses

date: 2017-01-25
slug: fix-wordpress-permissions
draft: false
---

Here’s the recommended permissions for [WordPress](https://codex.wordpress.org/Hardening_WordPress).

#### Permissions

Directories = 755  
Files = 644

#### Install From Scratch

If you’re starting from scratch, follow the instructions below.

Assuming you’re logged in as normal user. Use sudo to execute commands as superuser.

```
cd /var/www/
sudo wget https://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
sudo chown -R www-data:www-data wordpress
```

#### Fix Current

If your permissions are wrong, then perform the following.

```
sudo find /var/www/wordpress/ -type d -exec chmod 755 {} \
sudo find /var/www/wordpress/ -type f -exec chmod 644 {} \
```