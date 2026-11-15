---
title: 'restarting nginx'
author: ulysses

date: 2016-07-01
slug: restarting-nginx
draft: false
---

Niginx is primarily a web server, but it can also run as a proxy server, load balancer and a HTTP cache.

If you’re running on Debian, Ubuntu, Red Hat or CentOS, the following are several ways of restarting Nginx.

```
# /etc/init.d/nginx restart
# /etc/init.d/nginx reload
# service nginx restart
# service nginx reload
# nginx -s reload
```

The last example is more universal and will run in any Linux flavor.