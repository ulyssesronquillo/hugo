---
title: 'cant connect to mysql server'
author: ulysses

date: 2013-06-28
slug: cant-connect-to-mysql-server
draft: false
---

I recently had a problem with an Ubuntu server that was running MySQL. None of my applications were connecting to the database. After poking around in the server, I realized the database doesn’t seem to be running at all. I tried restarting it from the Terminal, but I ran into this error message.

```
ERROR 2003 (HY000): Can't connect to MySQL server on '10.10.10.110' (111)
```

As it turns out, the Ubuntu server picked up a new IP address of 10.10.10.113 from the last reboot. I went ahead and assigned a static IP address to the server of 10.10.10.200. I should have done it initially when I setup the server. If you need help setting up a static IP address on the Ubuntu server, here are the instructions on [how to set Ubuntu server to static IP address](http://ulyssesonline.com/ubuntu/2007/06/28/change-ip-address/).

I looked at the MySQL configuration file called /etc/mysql/my.cnf, the bind-address was manually set to the old IP address of 10.10.10.110. So, edited the file and entered the new IP address of 10.10.10.200.

```
bind-address = 10.10.10.200
```

Finally, I restarted the network as well as started the MySQL server.

```
sudo /etc/init.d/networking restart
sudo /etc/init.d/mysql start
```

Everything is hunky dory again.
