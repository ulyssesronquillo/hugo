---
title: 'aws cli autoscaler update'
author: ulysses

date: 2020-04-27
slug: aws-cli-autoscaler-update
draft: false
---

Here’s the AWS CLI command to set the Auto Scaling Group to a certain number for the minimum, maximum, and desired number of instances.

```
#!/bin/bash
# Format:  
# ./autoscaling.sh 3
# ./autoscaling.sh 0
int=$1
aws autoscaling update-auto-scaling-group \
--auto-scaling-group-name your-auto-scaling-group \
--min-size $int \
--max-size $int \
--desired-capacity $int \
--region us-east-2
```

Format:

```
./autoscaling.sh 0
./autoscaling.sh 3
```