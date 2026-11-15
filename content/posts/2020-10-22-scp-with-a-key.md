---
title: 'scp with a key'
author: ulysses

date: 2020-10-22
slug: scp-with-a-key
draft: false
---

SCP is a secure copy utility in Linux. You’ll need access to your system. In this example, a pem key is used to authenticate to a host. SCP copies filename.ext to the home directory of ec2-user. It’s important to add the target directory, otherwise it will not work.

Here’s how to use SCP with a key from local to server.

```
scp -i key.pem filename.ext user@server:/home/user
```

From server to local. Run the command from local machine.

```
scp user@server:/home/user/file.txt /local/directory
```