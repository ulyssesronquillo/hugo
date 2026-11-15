---
title: 'remove key from known_hosts'
author: ulysses

date: 2019-08-31
slug: remove-key-from-known_hosts
draft: false
---

If you’ve changed keys, you will need to delete a ssh key from /etc/known\_hosts file.

You can edit it manually using an editor such as vi or vim.

```
vim ~/.ssh/known_hosts
```

Or you can use ssh-keygen command with -R option to delete the hostname or IP address.

```
ssh-keygen -f "~/.ssh/known_hosts" -R "xxx.xxx.xxx.xxx"
```