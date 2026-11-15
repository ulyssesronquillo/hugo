---
title: 'sudo with no password'
author: ulysses

date: 2019-07-07
slug: sudo-with-no-password
draft: false
---

If you’re the only user on your system, you don’t need to be prompted every time you run the sudo command.

Add yourself to the sudoers file.

```
# create a new file
sudo visudo -f /etc/sudoers.d/users
```

Add this line.

```
# add your username
username ALL=(ALL) NOPASSWD:ALL
```

Exit and try again.

```
# exit out and login again
exit
# try to sudo again
sudo -i
# there's no password prompt for sudo this time
```