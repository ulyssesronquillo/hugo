---
title: 'php modules'
author: ulysses

date: 2020-05-07
slug: php-modules
draft: false
---

Here are some missing PHP modules on my WordPress install.

```
apt install php-gd php-dom php-mbstring php-imagick php-zip
```

Reboot Apache after the install.

```
systemctl restart apache2
```