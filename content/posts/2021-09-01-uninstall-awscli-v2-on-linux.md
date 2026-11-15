---
title: 'uninstall awscli v2 on linux'
author: ulysses

date: 2021-09-01
slug: uninstall-awscli-v2-on-linux
draft: false
---

How to uninstall AWSCLI version 2 on Linux

Locate aws.

```
$ which aws
/usr/local/bin/aws
```

Delete the symlinks.

```
$ ls -l /usr/local/bin/aws
$ sudo rm /usr/local/bin/aws
$ sudo rm /usr/local/bin/aws_completer
```

Delete the install directory.

```
$ sudo rm -rf /usr/local/aws-cli
```

Once deleted, you can reinstall awscli.