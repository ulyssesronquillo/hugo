---
title: 'https in codeigniter'
author: ulysses

date: 2019-07-17
slug: https-in-codeigniter
draft: false
---

If you switched to HTTPS in Apache, make sure to update CodeIgniter’s config file.

```
vim /var/www/applications/config/config.php
```

Change the base URL to https.

```
$config['base_url']	= 'https://yourdomain.com/ci/';
```