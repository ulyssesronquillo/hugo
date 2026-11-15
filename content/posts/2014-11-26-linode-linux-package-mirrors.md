---
title: 'linode linux package mirrors'
author: ulysses

date: 2014-11-26
slug: linode-linux-package-mirrors
draft: false
---

One way to speed up the Linux package updates is to use a package mirror made available by Linode. They are hosted in all six of their data centers. Just pick a data center where your data is Linode server is located by doing the following.

Edit your sources list

```
sudo nano /etc/apt/sources.list
```

Search and replace

```
# Replace this address 
http://us.archive.ubuntu.com/ubuntu/ 

# with the new address 
http://fremont.mirrors.linode.com/ubuntu/

# you can also use this - returns round robin of all locations
http://mirrors.linode.com/ubuntu/
```

The next time you run a Linux update, it will be significantly faster.

```
sudo apt-get update
sudo apt-get upgrade
```