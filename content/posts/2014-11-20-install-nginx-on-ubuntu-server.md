---
title: 'install nginx on ubuntu server'
author: ulysses

date: 2014-11-20
slug: install-nginx-on-ubuntu-server
draft: false
---

nginx (pronounced engine x) is an HTTP and reverse proxy server written by Igor Sysoev. nginx is gaining traction over the years due to its exceptional speed. The latest Netcraft web survey indicate that 14.42 percent of the Internet of websites runs on Nginx.

If you looking to replace your Apache web server or just want to play around with nginx, here are the really simple instructions on how to install nginx on any Ubuntu Server.

```
# run update
sudo apt-get update
sudo apt-get upgrade
# install nginx
sudo apt-get install nginx
# start nginx
sudo service nginx start
```

Open your browser and point it to the IP address of your Ubuntu Server.

You’ll see this if your installation was successful.

![nginx-page](http://uly.me/wp-content/uploads/2014/11/nginx-page.png)