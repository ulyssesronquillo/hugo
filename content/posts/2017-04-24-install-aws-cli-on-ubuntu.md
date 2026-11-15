---
title: 'install aws cli on ubuntu'
author: ulysses

date: 2017-04-24
slug: install-aws-cli-on-ubuntu
draft: false
---

The advantage of running Amazon Linux on AWS is that you already have the AWS CLI (command line interface) loaded as part of the image. In addition, Amazon Linux has rolling updates. It means you don’t have to perform major upgrades as you go to from one version to another. It’s all part of the process when you perform periodical updates. However, if you’re running Ubuntu, it’s no slouch. It’s a popular distro which many administrators have chosen to use due to its simplicity and robust repository. So, if you’re running Ubuntu, you might want to install the AWS CLI to give you the tools you need similar to what Amazon Linux has. Here’s how to install AWS CLI on Ubuntu.

```
$ sudo apt install awscli
```

You will need to run the configuration before you can start using AWS CLI. See example below.

```
$ sudo aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```

Obviously, you will need your own Access Key and Secret Key that you’ll need to generate from your AWS Console under IAM.