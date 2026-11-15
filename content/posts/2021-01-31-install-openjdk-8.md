---
title: 'install openjdk 8'
author: ulysses

date: 2021-01-31
slug: install-openjdk-8
draft: false
---

Here’s the installation instructions for OpenJDK 8.

For Fedora, Redhat and Oracle Linux.

```
yum install java-1.8.0-openjdk
```

For Debian and Ubuntu.

```
apt-get install openjdk-8-jre
```

To see if the packages (symbolic links) are there, they can be found in /etc/alternatives/, at least in Redhat 7.

```
ls -l /etc/alternatives/
```