---
title: 'wordpress permalinks on nginx'
author: ulysses

date: 2015-06-24
slug: wordpress-permalinks-on-nginx-2
draft: false
---

If you’re running WordPress on Nginx, you may have an issue with WordPress permalinks. This [article](http://nginxlibrary.com/wordpress-permalinks/) explains nicely what you need to do to configure Nginx. What the article failed to do is mention the Nginx configuration filename and its location. The filename is nginx.conf, and it’s usually located in the directory /usr/local/nginx/conf, /etc/nginx, or /usr/local/etc/nginx, depending on your Linux distro.

```
# WordPress installed on root directory
location / {
  index index.php index.html index.htm;
  try_files $uri $uri/ /index.php?$args;
}

# WordPress installed on /blog sub-directory
location /blog/ {
    try_files $uri $uri/ /blog/index.php?$args;
}
```

You need to reload Nginx for changes to take effect. For Ubuntu:

```
$ sudo service nginx restart
# or
$ sudo /etc/init.d/nginx restart
```