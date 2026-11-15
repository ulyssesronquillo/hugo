---
title: 'install s3cmd on mac'
author: ulysses

date: 2016-12-29
slug: install-s3cmd-on-mac
draft: false
---

Previously, I wrote about installing and accessing Amazon S3 (Simple Storage Service) from [Ubuntu](http://uly.me/install-s3cmd-on-ubuntu/) using s3cmd command line tool. Interestingly enough, the S3cmd command line tool is also available on the Mac, since MacOS is based on NeXT, which was based on BSD, which is a major variant of Unix. Anyways, you can install s3cmd on the Mac so you can access to Amazon S3 via the command line.

How to Install

```
$ sudo sudo python setup.py install
```

Configure

```
$ s3cmd --configure 
```

The configuration will ask you to provide your access key and secret key. You can get those keys from your AWS account or your AWS administrator.

Once it’s configured and you have access to the S3, you can try the following commands.

```
# list the files
$ s3cmd ls 
# get file sizes in human form
$ s3cmd du -H s3://yourbucket
# create a new bucket
$ s3cmd mb s3://newbucket
# put file into bucket
$ s3cmd put filename.ext s3://bucket/folder
# get file from bucket
$ s3cmd get s3://yourbucket/yourfolder/yourfile
# delete file from bucket
$ s3cmd del s3://yourbucket/yourfolder/yourfile
```

There are a lot more commands you can explore. Here’s the [documentation](http://s3tools.org/usage).