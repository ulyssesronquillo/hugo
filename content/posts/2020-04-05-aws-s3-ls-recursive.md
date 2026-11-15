---
title: 'aws s3 ls recursive'
author: ulysses

date: 2020-04-05
slug: aws-s3-ls-recursive
draft: false
---

Here’s how to list S3 files recursively.

```
aws s3 ls s3://mybucket --recursive | awk '{print $4}'
```

By default, the results display date, time, disk size and filename. Use awk to display the filename only.