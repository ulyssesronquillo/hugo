---
author: ulysses
title: 'gcloud could not setup log file'
date: 2025-01-06
slug: gcloud-could-not-setup-log-file
draft: false
---

I was getting this error whenever Apache runs a gcloud command.

```
WARNING: Could not setup log file in /usr/share/httpd/.config/gcloud/logs, 
(Error: Could not create directory [/usr/share/httpd/.config/gcloud/logs/2025.01.06]: Permission denied.

Please verify that you have permissions to write to the parent directory..
The configuration directory may not be writable. To learn more, see https://cloud.google.com/sdk/docs/configurations#creating_a_configuration
ERROR: (gcloud.compute.disks.list) Could not create directory [/usr/share/httpd/.config/gcloud]: Permission denied.

Please verify that you have permissions to write to the parent directory.
```

So, here's the fix. The .config directory under /usr/share/httpd/ is missing.

```
mkdir /usr/share/httpd/.config
chown -R apache:apache /usr/share/httpd/.config 
```

Create the directory and change ownership to apache:apache.

