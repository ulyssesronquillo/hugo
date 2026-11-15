---
title: 'lock a package in linux'
author: ulysses

date: 2022-01-07
slug: lock-a-package-in-linux
draft: false
---

Here’s how to lockdown a package to a specific version.

Search for the current package.

```
$ sudo rpm -qa |  grep sdk
google-cloud-sdk-365.0.1-1.x86_64
```

Install versionlock.

```
yum install yum-plugin-versionlock
```

Lock a package.

```
yum versionlock google-cloud-sdk-365.0.1-1.x86_64
```

Display all locked versions.

```
yum versionlock list
```

Unlock and clear.

```
yum versionlock clear
```