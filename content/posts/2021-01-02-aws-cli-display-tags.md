---
title: 'aws cli display tags'
author: ulysses

date: 2021-01-02
slug: aws-cli-display-tags
draft: false
---

This command lists the EC2 instance id and the tag name using query.

```
aws ec2 describe-instances \
--query 'Reservations[].Instances[].[InstanceId,Tags[?Key==Name]|[0].Value]' \
--profile tfc \
--region us-east-2 \
--output text
```

Output:

```
i-xxxxxxxxxxxxxxxxx     server-one
i-xxxxxxxxxxxxxxxxx     server-two
i-xxxxxxxxxxxxxxxxx     server-three
```

|\[0\].Value insures output is one instance record per line.