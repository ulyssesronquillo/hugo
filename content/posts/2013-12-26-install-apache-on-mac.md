---
title: 'install apache on mac'
author: ulysses

date: 2013-12-26
slug: install-apache-on-mac
draft: false
---

This article will show you how to install Apache on the Mac OS. This is ideal if you want to use your Mac desktop or laptop as your development environment, a place where you can test code, scripts, themes, plugins without affecting your production environment.

> This article is part of a series of articles on how to manually install MAMP or Apache, PHP, MySQL on the Mac OS. Installing the popular MAMP application is as simple as installing any other application on the Mac, but it will not give you any valuable learning experience, nor will you have complete control of your development environment. I recommend manually installing the individual applications to maximize your learning experience.

[Apache](http://httpd.apache.org) is the widely popular web server that runs on multiple platforms including Linux, Mac OS and Windows. Some people might be surprised to know that Apache is already installed and included on the latest Mac OS X Mavericks. All you need to do is turn it on. You can do so by accessing the Terminal and typing the following:

#### How to Install Apache on Mac OS X

#### Start Apache

```
$ sudo apachectl start
```

You should be able to see ‘**It works!**‘ if you access ‘**http://localhost**‘ from your Safari, Chrome or Firefox browser.

In addition, you can also stop and restart Apache using the commands below.

#### Stop Apache

```
$ sudo apachectl stop
```

#### Restart Apache

```
$ sudo apachectl restart
```

By default, the web root for the Apache web server is located at ‘**/Library/WebServer/Documents/**.’ In the directory, you’ll find a document called ‘**index.html.en**‘ which contains the code that displays ‘**It works!**‘

```
<h1>It works!</h1>
```

#### It works!

Finally, you can now move your HTML pages to the ‘**/Library/WebServer/Documents/**‘ folder to serve pages. The other option is to create a virtual host within Apache which I will cover in my next article.