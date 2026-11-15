---
title: 'delete .ds_store files recursively'
author: ulysses

date: 2013-01-31
slug: delete-ds_store-files-recursively
draft: false
---

If you work with MacOS and you FTP files to a Linux server, you probably have seen this pesky and ubiquitous hidden files named .DS\_Store. They seem to be in every folder known to man. The .DS\_Store files are hidden MacOS files used to store the attributes of a folder such as position of icons and choice of background images, etc. Although they are not harmful, they probably don’t belong on the web server. Instead of deleting them one by one, there’s a faster way of deleting them recursively. You can invoke this command from the Linux terminal on your webroot folder.

```
cd /var/www/
find . "-name" ".DS_Store" -exec rm {} \;
```

The .DS\_Store files will be deleted recursively.