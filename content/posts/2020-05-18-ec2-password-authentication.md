---
title: 'ec2 password authentication'
author: ulysses

date: 2020-05-18
slug: ec2-password-authentication
draft: false
---

When you stand up an AWS instance, it’s only accessible via SSH key using the default user, typically ec2-user.

Add password to ec2-user, then enable password authentication to ‘yes’ in SSH.

```
# Add password to ec2-user
sudo passwd ec2-user
# edit ssh config
vim /etc/ssh/sshd_config
# enable password authentication
PasswordAuthentication yes
# save file and exit
```

Restart SSH service.

```
systemctl restart sshd.service
```