---
title: 'aws efs tags'
author: ulysses

date: 2021-01-04
slug: aws-efs-tags
draft: false
---

This script add new tags if they are missing.

```
#!/bin/bash
log="log.txt"
id=$(aws efs describe-file-systems --query "FileSystems[*].[FileSystemId]" --output text --region us-east-1)
tag=$(aws efs describe-file-systems --query "FileSystems[*].Tags[?Key=='aws-backup'].Value" --output text --region us-east-1 )

arr[0]="efs-0000"
arr[1]="efs-0400"
arr[2]="efs-0800"
arr[3]="efs-1200"
arr[4]="efs-1600"
arr[5]="efs-2000"

rand=$[ $RANDOM %6 ]
backup=${arr[$rand]}

if [[ $tag == "" ]]; then
  aws efs tag-resource --resource-id $id --tags Key="aws-backup",Value=${arr[$rand]} --profile default --region us-east-1
  echo "Added backup tag $backup to $id" 
elif [[ $tag == "no-backup" ]]; then
  echo "No backup on $id."
else
  echo "No changes done to $id."
fi
```