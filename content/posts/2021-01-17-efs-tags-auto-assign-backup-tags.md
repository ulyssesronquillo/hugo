---
title: 'efs tags auto assign backup tags'
author: ulysses

date: 2021-01-17
slug: efs-tags-auto-assign-backup-tags
draft: false
---

Here’s a script that scans all EFS systems in several AWS accounts and regions and randomly assigns backup tags to EFS systems that are missing backup tags. This is assuming EFS is using AWS Backup service using tags to apply backup policies. If there are no backup tags, an EFS gets assigned a randomly picked backup policy.

```
#!/bin/bash
# log file
output="test.log"
tmpfil="temp.txt"
# empty file
> $output
# set random array
arr[0]="efs-0000"
arr[1]="efs-0400"
arr[2]="efs-0800"
arr[3]="efs-1200"
arr[4]="efs-1600"
arr[5]="efs-2000"
rand=$[ $RANDOM %6 ]
backup=${arr[$rand]}
# set accounts and regions
declare -a account=("default" "one" "two" "three" "four" "five")
declare -a region=("us-east-1" "us-east-2" "us-west-1" "us-west-2")
for i in "${account[@]}"; do
  echo "===================" >> $output
  echo $i >> $output
  echo "===================" >> $output
  for j in "${region[@]}"; do
    echo $j >> $output
        aws efs describe-file-systems \
        --query "FileSystems[*].[FileSystemId,Tags[?Key=='aws-backup']|[0].Value]" \
        --profile $i \
        --region $j \
        --output text > $tmpfil
        while read -r id tag; do
      if [[ $tag == "" ]]; then
        aws efs tag-resource \
        --resource-id $id \
        --tags Key="aws-backup",Value=${arr[$rand]} \
        --profile $i \
        --region $j >> $output
        echo "Added backup tag $backup to $id" >> $output
      elif [[ $tag == "no-backup" ]]; then
        echo "Backup tag is already set to no-backup on $id." >> $output
      else
        echo "No backup tag changes applied to $id." >> $output
      fi
    done
```