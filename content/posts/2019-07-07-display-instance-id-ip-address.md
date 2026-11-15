---
title: 'display instance id and ip address'
author: ulysses

date: 2019-07-07
slug: display-instance-id-ip-address
draft: false
---

How to display IP address and Instance ID on web page behind a AWS load balancer.

Add these 2 commands in crontab. The job runs every 5 mins.

```
*/5 * * * * /usr/bin/curl http://169.254.169.254/latest/meta-data/instance-id > /var/www/html/id.txt
*/5 * * * * /usr/bin/curl http://169.254.169.254/latest/meta-data/public-ipv4 > /var/www/html/ip.txt
```

You can view on the site.

```
# your domain
http://yourdomain.com/ip.txt
http://yourdomain.com/id.txt
# your server ip address
http://1.1.1.1/ip.txt
http://1.1.1.1/id.txt
```
