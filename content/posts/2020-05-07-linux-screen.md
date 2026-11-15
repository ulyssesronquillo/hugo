---
title: 'linux screen'
author: ulysses

date: 2020-05-07
slug: linux-screen
draft: false
---

If you don’t have it installed.

```
yum install screen
apt install screen
```

Before you run a process, run screen, and detach.

```
screen
# run the command
ping yahoo.com
# ctrl-a and ctrl-d to detach
```

To reattach, get a list of screen sessions, and attach to it.

```
screen -ls
# result is somewhat similar to below
4452.hostname
# attach to it
screen -dr 4452.hostname
```

To stop, just type exit from the screen terminal.