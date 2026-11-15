---
title: 'linux screen'
author: ulysses

date: 2022-12-26
slug: linux-screen-2
draft: false
---

Just documenting the Linux Screen command.

Install screen first.

```
yum install screen
dnf install screen
apt install screen
zypper install screen
```

Start a new screen.

```
screen -S one
screen -S two
screen -S three
```

Detach from screen.

```
Ctrl+a+d
```

List active screens.

```
screen -ls 
There is a screen on:
        15575.one   (Detached)
        15581.two   (Detached)
        15593.three (Detached)
1 Socket in /var/run/screen/S-root.
```

Reattach to an existing screen.

```
screen -r one
screen -r two
screen -r three
```

If there’s only one active screen, you can run screen -r without the name.

```
screen -r 
```

To exit or quit a screen, reattach and run exit.

```
screen -r three
# exit
[screen is terminating]
```