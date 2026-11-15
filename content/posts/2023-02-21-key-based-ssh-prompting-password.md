---
title: 'key-based ssh prompting password'
author: ulysses

date: 2023-02-21
slug: key-based-ssh-prompting-password
draft: false
---

Key-based SSH login is prompting a password despite it’s already setup to use keys. As turns out, the home directory was changed to 777. To fix, I changed home folder permissions and restarted SSH. It probably does not need a restart, but it doesn’t hurt.

```
chown -R username:username /home/username
find /home/username -type d -exec chmod 755 {} \;
find /home/username -type f -exec chmod 644 {} \;
```

```
sudo systemctl restart ssh
```