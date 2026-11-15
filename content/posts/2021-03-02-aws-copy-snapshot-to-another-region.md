---
title: 'aws copy snapshot to another region'
author: ulysses

date: 2021-03-02
slug: aws-copy-snapshot-to-another-region
draft: false
---

If you need to copy a snapshot from one region to another, here’s the AWS CLI command.

```
aws ec2 copy-snapshot \
    --region us-east-1 \
    --source-region us-east-2 \
    --source-snapshot-id snap-xxxxxxxxxxxxxxxxx \
    --description "This is the DR snapshot copy"
```

Output:

```
{
    "SnapshotId": "snap-xxxxxxxxxxxxxxxxx"
}
```