---
title: 'aws s3 bucket permission'
author: ulysses

date: 2021-02-16
slug: aws-s3-bucket-permission
draft: false
---

I was getting this error when downloading a file from a S3 bucket.

```
fatal error: An error occurred (403) when calling the HeadObject operation: Forbidden
```

Turns out to be a permission issue. Use –acl bucket-owner-full-control.

```
# UPLOAD
aws s3 cp file.txt s3://bucket-name/dir/ --acl bucket-owner-full-control
upload: .\file.txt to s3://bucket-name/dir/fw.sh
# DOWNLOAD
aws s3 cp s3://bucket-name/dir/file.txt . --acl bucket-owner-full-control
download: s3://bucket-name/dir/file.txt to .\file.txt
```

You need to do for both upload and download.