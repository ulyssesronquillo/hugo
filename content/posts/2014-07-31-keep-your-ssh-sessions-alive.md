---
title: 'keep your ssh sessions alive'
author: ulysses

date: 2014-07-31
slug: keep-your-ssh-sessions-alive
draft: false
---

If you work on servers via Terminal using SSH (secure shell), one of the more annoying things that happens quite regularly are timeouts. If there’s no activity between your SSH client and the server, your terminal is closed because your session has timed out. You’ll need to login again. If you do this at least 6 times a day, then you can see how taxing this whole exercise can be.

To avoid Terminal timeouts, you can set the SSH client, your terminal, to keep the connection alive by sending a null signal to the server every few seconds. I’ve set mine to 2 minutes. Since I’m on Mac OS, I’ll need to configure my SSH client. The configuration file is located in your home directory under .ssh/config. If the file doesn’t exist, just create one.

```
cd
nano .ssh/config
```

Now add the following lines to it.

```
Host *
ServerAliveInterval 120
```

I’ve set mine to 120 seconds or 2 minutes. This value works for me while connected to an Ubuntu Server. You may have to play around with this value on other Linux systems. I think this is a better approach as opposed to configuring the SSH server on every server you are connected to. You may not have root access to some servers. Changing the settings on your SSH client is the better approach.