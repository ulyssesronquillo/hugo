---
title: 'install s3cmd on ubuntu'
author: ulysses

date: 2014-12-22
slug: install-s3cmd-on-ubuntu
draft: false
---

If you want to backup your Linux server to Amazon S3 (Simple Storage Service), you need to install a utility called S3cmd which allows you to interact with Amazon’s cloud storage service. You’ll be able to create s3 buckets, upload and retrieve files from your Linux server to the S3.

You can install S3cmd from Ubuntu.

```
sudo apt-get install s3cmd
```

Next, you need to configure S3cmd using your S3 credentials. You’ll need an Access key and a Secret key from Amazon’s Security Credentials page which you can access from Amazon’s IAM Management Console.

```
sudo s3cmd --configure
```

For details on how to fully implement S3cmd, please take a look at this [article](http://tecadmin.net/install-s3cmd-manage-amazon-s3-buckets/).