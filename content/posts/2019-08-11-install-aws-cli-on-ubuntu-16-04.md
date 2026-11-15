---
title: 'install aws cli on ubuntu 16.04'
author: ulysses

date: 2019-08-11
slug: install-aws-cli-on-ubuntu-16-04
draft: false
---

I ran into an issue with AWS CLI on Ubuntu 16.04. I was getting this error, “AWSHTTPSConnection’ object has no attribute ‘ssl\_context” every time I try to do a simple “aws s3 ls” command. So, here’s the fix.

Assuming you installed “awscli” using apt. Go ahead and uninstall it.

```
apt remove awscli
```

Install awscli using pip instead.

```
apt install python-pip
pip install awscli
aws --version
```

If this is a fresh install, you may have to run “aws configure.”