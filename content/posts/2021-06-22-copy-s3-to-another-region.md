---
title: 'copy s3 to another region'
author: ulysses

date: 2021-06-22
slug: copy-s3-to-another-region
draft: false
---

Buckets are regional. Your source and destination buckets should be in different regions.

```
aws s3 sync s3://DOC-EXAMPLE-BUCKET-SOURCE s3://DOC-EXAMPLE-BUCKET-TARGET
```

Use the sync command. It will copy new or modified files.