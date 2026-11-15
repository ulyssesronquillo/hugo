---
title: 'wordpress permalinks on nginx'
author: ulysses

date: 2014-11-25
slug: wordpress-permalinks-on-nginx
draft: false
---

You’ve abandoned Apache for a faster, newer and sleeker Nginx. Installation was a breeze. WordPress is just humming along until you start clicking links within WordPress. You realized the permalinks are broken, which is a biggie. So, here’s how you fix WordPress permalinks on Nginx.

WordPress on root directory

```
# Edit nginx config
sudo nano /etc/nginx/sites-available/default
```

```
# Add the following lines to the file.
location / {
index index.php index.html index.htm;
try_files $uri $uri/ /index.php?args;
}
```

WordPress in a subdirectory under root

```
location /wordpress/ {
try_files $uri $uri/ /wordpress/index.php?args;
}
```

Restart Nginx

```
# must restart nginx for the changes to take effect
sudo nano service nginx restart
```