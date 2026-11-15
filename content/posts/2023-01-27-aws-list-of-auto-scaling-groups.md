---
title: 'aws list of auto scaling groups'
author: ulysses

date: 2023-01-27
slug: aws-list-of-auto-scaling-groups
draft: false
---

Here’s a script to list Auto Scaling Groups from multiple AWS accounts. Accounts are in your AWS profiles.

```
#!/bin/bash
file='results-aws-asg.txt'
> $file
declare -a account=("default" "account-1" "account-2" "account-3" "account-4" "account-5")
declare -a region=("us-east-1" "us-east-2" "us-west-1" "us-west-2")
for i in "${account[@]}"
do
    echo '----------------------' >> $file
    echo 'Account: '$i >> $file
    for j in "${region[@]}"
    do
        echo 'Region: '$j >> $file
        aws autoscaling describe-auto-scaling-groups \
        --query "AutoScalingGroups[].[AutoScalingGroupName,LaunchConfigurationName]" \
        --profile $i \
        --region $j \
        --output text >> $file
    done
done
```