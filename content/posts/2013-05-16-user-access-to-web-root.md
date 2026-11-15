---
title: 'user access to web root'
author: ulysses

date: 2013-05-16
slug: user-access-to-web-root
draft: false
---

When setting up your Ubuntu server, you can allow regular Linux accounts to access your web root directory via FTP or secure shell. In this case, you want users to access /var/www directory. One of the first things you’ll need to do is give permissions to the Apache user www-data.

Change the group name to /var/www.

```
sudo chgrp www-data /var/www
```

Make it writeable.

```
sudo chmod 775 /var/www
```

Set the GID for www-data for all sub-folders.

```
sudo chmod g+s /var/www
```

Finally, add your user to www-data group.

```
sudo usermod -a -G www-data username
```

This will now allow you to use a regular user account via FTP or SSH with write permissions to the /var/www directory. This is much more secure way than using the www-data user account.