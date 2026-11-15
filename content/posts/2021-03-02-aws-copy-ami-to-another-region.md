---
title: 'aws copy ami to another region'
author: ulysses

date: 2021-03-02
slug: aws-copy-ami-to-another-region
draft: false
---

Here’s how to copy an AMI to another region.

```
aws ec2 copy-image \
  --source-image-id ami-xxxxxxxxxxx \
  --source-region us-east-1 \
  --region us-east-2 \
  --name "My DR server"
```

Output:

```
{
    "ImageId": "ami-xxxxxxxxxxx"
}
```