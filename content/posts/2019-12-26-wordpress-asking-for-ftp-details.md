---
title: 'wordpress asking for ftp details'
author: ulysses

date: 2019-12-26
slug: wordpress-asking-for-ftp-details
draft: false
---

If WordPress is asking for FTP details when you’re trying to update a theme, plugin, or WordPress itself, you will need to edit your wp-config.php file to add the following line to your configuration.

```
define('FS_METHOD','direct');
```

Save the file and try updating again. It shouldn’t ask you for FTP details.