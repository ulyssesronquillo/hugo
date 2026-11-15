---
author: ulysses
title: 'install xrdp'
date: 2024-01-11
slug: install-xrdp
draft: false
---

xrdp is a package that allows another desktop to connect to another using the rdp desktop software. 

Install xrdp on the target desktop.

```
sudo apt install xrdp
```

Add a second user since you can't use the default user. Use -m to create a home directory.

```
sudo useradd -m john
```

Give new user sudo access. This is optional, but is nice to have if running root commands.

```
sudo usermod -a -G sudo john
```

Set the user's password.

```
sudo passwd john
```

You can now connect from a rdp client to your desktop using username john.
