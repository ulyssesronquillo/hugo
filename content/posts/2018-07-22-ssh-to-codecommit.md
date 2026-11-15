---
title: 'ssh to codecommit'
author: ulysses

date: 2018-07-22
slug: ssh-to-codecommit
draft: false
---

Although you can access CodeCommit from the AWS Console, the most efficient way to access it, is via SSH. Assuming you already have an IAM user, as well as Git installed on your local machine, it’s time to setup a SSH connection to CodeCommit by performing the following commands.

1. Generate a RSA key pair
2. Copy the public key to the clipboard.
3. Upload the SSH public key to the AWS IAM Console.
4. You’ll receive a SSH Key ID.
5. Create a config file
6. chmod 600 config
7. Test connection
8. Clone repo

To get more details regarding SSH access to CodeCommit, visit the AWS [docs](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-ssh-unixes.html).