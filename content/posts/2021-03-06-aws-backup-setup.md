---
title: 'aws backup setup'
author: ulysses

date: 2021-03-06
slug: aws-backup-setup
draft: false
---

This script creates an AWS backup vault, adds a backup plan and a backup selection.

Set up profile, region and Account ID first.

```
#!/bin/bash
profile="default"
region="us-east-1"
id=$(aws sts get-caller-identity --query Account --output text)
```

Create a vault.

```
aws backup create-backup-vault \
--backup-vault-name my-vault \
--profile $profile \
--region $region
```

Create a backup plan.

```
aws backup create-backup-plan \
--backup-plan file://back-plan.json \ 
--profile $profile \
--region $region
```

backup-plan.json

```
{
    "BackupPlan": {
        "BackupPlanName": "efs-0000",
        "Rules": [
            {
                "RuleName": "efs-0000",
                "TargetBackupVaultName": "my-vault",
                "ScheduleExpression": "cron(0 0 ? * * *)",
                "StartWindowMinutes": 60,
                "CompletionWindowMinutes": 10080,
                "Lifecycle": {
                    "DeleteAfterDays": 7
                }
            }
        ]
    }
}
```

Get the backup plan ID.

```
planid=$(aws backup list-backup-plans \
  --query "BackupPlansList[?BackupPlanName=='efs-0000'].BackupPlanId" \
  --profile $profile \
  --region $region \
  --output text)
```

Create a backup selection.

```
# Create a backup selection
aws backup create-backup-selection \
--backup-plan-id $planid \
--cli-input-json file://backup-selection.json \
--profile $profile \
--region $region
```

backup-selection.json

```
{
    "BackupSelection": {
		"SelectionName": "efs-0000",
        "IamRoleArn": "arn:aws:iam::xxxxxxxxxxxx:role/service-role/AWSBackupDefaultServiceRole",
        "Resources": [],
        "ListOfTags": [
            {
                "ConditionType": "STRINGEQUALS",
                "ConditionKey": "aws-backup",
                "ConditionValue": "efs-0000"
            }
        ]
    }
}
```

The enable EFS backup, add a tag key of **aws-backup** with a value of **efs-0000**.