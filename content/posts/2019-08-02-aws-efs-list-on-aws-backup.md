---
title: 'aws efs list on aws backup'
author: ulysses

date: 2019-08-02
slug: aws-efs-list-on-aws-backup
draft: false
---

Here’s how to get a list of EFS on AWS Backup. Displays a list and looks for a specific tag.

```
#! /bin/bash

tmpfil="temp.txt"
output="efs-list.txt"

> $output
> $tmpfil

declare -a account=("default" "account1" "account2" "account3")
declare -a region=("us-east-1" "us-east-2" "us-west-1" "us-west-2")

for i in "${account[@]}"; do
  echo "===================" >> $output
  echo $i >> $output
  echo "===================" >> $output
  for j in "${region[@]}"; do
    echo $j >> $output
    echo "-------------------" >> $output
    aws efs describe-file-systems \
    --query 'FileSystems[*].[FileSystemId]' \
    --profile $i --region $j --output text >> $tmpfil
    while read -r efs; do
      echo $efs >> $output
      sleep 1s
      aws efs describe-tags --file-system-id $efs \
      --query 'Tags[?Key==`aws-backup`].{Name:Key,Value:Value}' \
      --profile $i --region $j --output text >> $output
      echo "..................." >> $output
    done  $tmpfil
  done
done
rm $tmpfil
```

Output file is efs-list.txt