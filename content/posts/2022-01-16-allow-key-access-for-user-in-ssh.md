---
title: 'allow key access for user in ssh'
author: ulysses

date: 2022-01-16
slug: allow-key-access-for-user-in-ssh
draft: false
---

Allow shared key access only for one user in SSH.

Disable the password authentication for one user in your SSH config. Edit /etc/ssh/sshd\_config.

```
Match User username
  PasswordAuthentication no
```

Restart the SSH service.

```
service ssh restart
```

Copy user’s public key to the destination server’s authorized file in ~/.ssh/authorized\_keys.

```
ssh-rsa AAAAxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 
```

Back on your client, login via SSH. User will not be prompted for password since public key is already authorized on server.

```
ssh username@server

```