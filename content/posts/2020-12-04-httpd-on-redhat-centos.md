---
title: 'httpd on redhat and centos'
author: ulysses

date: 2020-12-04
slug: httpd-on-redhat-centos
draft: false
---

Here are the commands to start, stop, enable and get the status of Apache on RHEL and CentOS.

```
systemctl enable httpd  # enable on bootup
systemctl status httpd  # get status
systemctl start httpd   # start
systemctl stop httpd    # stop
systemctl restart httpd # restart
```
