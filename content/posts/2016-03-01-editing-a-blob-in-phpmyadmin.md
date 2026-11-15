---
title: 'editing a blob in phpmyadmin'
author: ulysses

date: 2016-03-01
slug: editing-a-blob-in-phpmyadmin
draft: false
---

One of my projects this week requires editing a blob. A blob is a binary large object used primarily for storing images, audio and other media types in the database. Unfortunately, the application didn’t allow me to edit a blob. So off to the PHPMyAdmin I went. PHPMyAdmin is a MySQL administration tool.

By default, the blob entries in PHPMyAdmin can’t be edited. Simple texts in blobs are sometimes scrambled. In order to make changes to the blob entries, we need to reconfigure PHPMyAdmin by editing the configuration file.

Edit the /etc/phpmyadmin/config.inc.php file.

```
$ sudo nano /etc/phpmyadmin/config.inc.php
```

Add the following entries at the end of the file.

```
$cfg['ProtectBinary'] = FALSE;
$cfg['DisplayBinaryAsHex'] = FALSE;
$cfg['ShowBlob'] = TRUE;
```

There is no need to restart any services. Changes are automatically reflected in PHPMyAdmin.