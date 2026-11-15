---
title: 'sftp with aws keys'
author: ulysses

date: 2019-07-24
slug: sftp-with-aws-keys
draft: false
---

How to use SFTP with AWS Keys.

```
sftp -i "yourkey" ec2-user@your-server
```

To copy files to server. File will copied to user’s home directory.

```
sftp> put file.txt .
```