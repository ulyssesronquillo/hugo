---
title: 'install cockpit on rocky 9'
author: ulysses

date: 2022-10-03
slug: install-cockpit-on-rocky-9
draft: false
---

Cockpit is a web-based graphical interface for Linux users and admins.

Install

```
dnf install cockpit
```

Start and Enable

```
systemctl start cockpit
systemctl enable cockpit.socket
```

Status

```
systemctl status cockpit
```

Web access

```
http://192.168.0.20:9090
```