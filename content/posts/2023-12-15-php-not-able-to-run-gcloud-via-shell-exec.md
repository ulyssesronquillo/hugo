---
author: ulysses
title: 'php not able to run gcloud commands via shell_exec'
date: 2023-12-15
slug: php-not-able-to-run-gcloud-via-shell-exec
draft: false
---

I ran into an issue with PHP not able to run gcloud commands via shell_exec. It turned out to be a permission issue.

I ended up granting the **apache** user access to **/usr/share/httpd/.config** directory which was missing. 

Google SDK needs write access to this directory. I ran the commands below and it worked after the changes.

```
mkdir /usr/share/httpd/.config
chown apache:root /usr/share/httpd/.config
```


