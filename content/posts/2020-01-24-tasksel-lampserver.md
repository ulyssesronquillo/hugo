---
title: 'tasksel lampserver'
author: ulysses

date: 2020-01-24
slug: tasksel-lampserver
draft: false
---

[Tasksel](http://wiki.debian.org/tasksel) is a Debian/Ubuntu tool that installs multiple related packages as a co-ordinated “task” onto your system. It’s similar to meta-packages where tasks are dericed from from Ubuntu package managers like Synaptic or KPackageKit.

Here’s a quickway to install a lamp server.

```
# install tasksel first if you don't have it.
apt install tasksel
# install a lamp server package
tasksel install lamp-server
```