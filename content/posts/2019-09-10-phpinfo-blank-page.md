---
title: 'phpinfo blank page'
author: ulysses

date: 2019-09-10
slug: phpinfo-blank-page
draft: false
---

Here’s how to fix when phpinfo is displaying a blank page. The install is missing this php module.

```
apt install php libapache2-mod-php
```

Restart after install.

```
service apache2 restart
```