---
title: 'aws cli s3 recursive copy'
author: ulysses

date: 2020-02-02
slug: aws-cli-s3-recursive-copy
draft: false
---

Here’s how to copy multiple files recursively using AWS CLI. The S3 cp command by default only copies a single file. To copy multiple files, you have to use the –recursive option along with –exclude and –include. In this example, we will exclude every file, but include only files with a json extension.

```
aws s3 cp /tmp/folder s3://bucket/folder \
  --recursive
  --exclude "*"
  --include "*.json"
```

The result:

```
upload: ./abc.json to s3://bucket/folder/abc.json    
upload: ./xyz.json to s3://bucket/folder/xyz.json
```