---
title: 'how to rotate apache logs'
author: ulysses

date: 2017-02-15
slug: how-to-rotate-apache-logs
draft: false
---

Apache comes with a logrotate utility. You can customize the way logrotate behaves by editing the /etc/logrotate.d/apache file. The logrotate utility has many options. In this example, we are rotating the log files that are located at the /var/www/domain.com/log/ directory. We are instructing the log files to rotate monthly for a total of 24 times. We are compressing the files by zipping them. We are using the date extension as part of the filename. We are also delaying the compression until the log has been rotated at least twice. Finally, Apache is restarted.

```
$ sudo nano /etc/logrotate.d/apache
/var/www/domain.com/*.log {
  monthly
  missingok
  rotate 24
  dateext
  compress
  delaycompress
  notifempty
  create 640 root adm
  sharedscripts
  postrotate
    if /etc/init.d/apache2 status > /dev/null ; then \
      /etc/init.d/apache2 reload > /dev/null; \
    fi;
  endscript
  prerotate
    if [ -d /etc/logrotate.d/httpd-prerotate ]; then \
      run-parts /etc/logrotate.d/httpd-prerotate; \
    fi; \
  endscript
}
```

To learn more about the logrotate utility, please visit the [documentation](http://www.linuxcommand.org/man_pages/logrotate8.html).