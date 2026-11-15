---
title: 'laravel: curl and mycrypt'
author: ulysses

date: 2014-08-08
slug: laravel-curl-and-mycrypt
draft: false
---

I’ve installed Laravel at least a dozen times. Each time, there’s always something new that goes awry during the installation. If it’s not curl, it’s mcrypt, or maybe the app/storage permissions. I think it’s just the fact that I’m experimenting where to put the Laravel files each time I install. It’s either /var/www or /home/user/. I’m using the Ubuntu standard PHP5 install. You have to specifically install php5-curl in addition to the standard PHP package. I think mcrypt is already in the PHP5 package, but to be sure I added it to the install. Here’s the command.

PHP

```
sudo apt-get install php5 php5-curl php5-mcrypt
```

App/storage

```
cd /home/user/laravel/app/
chmod -R o+x storage
```

These two things seem to solve most of the Laravel installation issues.