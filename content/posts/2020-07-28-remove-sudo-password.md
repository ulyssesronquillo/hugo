---
title: 'remove sudo password'
author: ulysses

date: 2020-07-28
slug: remove-sudo-password
draft: false
---

Removing sudo password is typically not a good practice. If you’re a seasoned system administrator, or you’re the only one using your own desktop, being prompted for a sudo password can get really annoying. Here’s how to stop getting prompted every time you run sudo.

Run visudo.

```
sudo visudo
```

Edit the sudo line and set to below.

```
%sudo ALL=(ALL) NOPASSWD: ALL
```

Save file.