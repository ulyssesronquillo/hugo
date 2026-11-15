---
title: 'aws list machine images'
author: ulysses

date: 2021-02-27
slug: aws-list-machine-images
draft: false
---

Here’s how to list AWS AMI (machine images) owned by yourself.

```
aws ec2 describe-images \
--query "Images[*].[Name,PlatformDetails]" \
--owners self \
--profile default \
--region us-east-1 \
--output text
```

Output:

```
icecast-0.1     Linux/UNIX
jekyll-0.3      Linux/UNIX
docker-0.1      Linux/UNIX
```

Specifying owners as self only display images owned by you.