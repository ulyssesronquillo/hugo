---
title: 'mac os hosts file'
author: ulysses

date: 2013-07-28
slug: mac-os-hosts-file
draft: false
---

Adding host entries in your desktop can be beneficial if you run several servers or hosts on your internal network. Instead of typing and remembering long IP addresses, you simply type the name of each host to make things easier for you. Let’s say you have several servers named “one”, “two” and “three” in your internal network. Each hosts will have their own assigned static IP address. By editing your hosts file and adding host entries to it, you can then use the hostnames instead of IP addresses.

In the end, you can ping each hostname like this:

```
$ ping one
$ ping two
$ ping three
```

In addition, you can also use the hosts “one”, “two” or “three” on your browser URL if your host has a web interface. If there are no host entries, the ping command, as well as you browser will simply timeout. To make this all possible in your Mac OS, you’ll need to edit the **/private/etc/hosts** file, by opening the Terminal and typing:

```
$ sudo nano /private/etc/hosts
```

You need to add each host to the file in this format: ip\_address hostname. See below:

```
192.168.1.22 one
192.168.5.56 two
192.168.1.33 three
```

Save file and exit. Ctrl-o and Ctrl-x.

Flush the DNS by typing:

```
$ dscacheutil -flushcache
```

You can now ping and use the hostname anyway you want.

The only limitation with this approach is, you’ll have to edit the hosts file for each desktop or laptop that is on your network. You can avoid this by take the next step, by running your own internal DNS server.