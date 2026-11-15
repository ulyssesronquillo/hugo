---
title: 'delete a symbolic link'
author: ulysses

date: 2014-11-21
slug: delete-a-symbolic-link
draft: false
---

In the Unix world, a symbolic is special type of file that references to another file or directory. Symbolic links are also known to others as symlink or softlink. To create a symbolic link, the ln -s command is used to reference a file to another like below.

```
sudo ln -s /usr/share/phpmyadmin/ /var/www/phpmyadmin
```

To delete a symbolic link

```
sudo rm /var/www/phpmyadmin
# or
sudo unlink /var/www/phpmyadmin
```