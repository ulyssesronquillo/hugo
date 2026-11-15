---
title: 'aws create backup plan'
author: ulysses

date: 2021-01-06
slug: aws-create-backup-plan
draft: false
---

After you created a backup vault, it’s time to create a backup plan. Here are a few examples.

```
aws backup create-backup-plan \
--cli-input-json file://backup-plan.json \
--profile default \
--region us-east-1
```

File: backup-plan.json

```
{
    "BackupPlan": {
        "BackupPlanName": "efs-0123",
        "Rules": [
            {
                "RuleName": "efs-0123",
                "TargetBackupVaultName": "efs-vault",
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

Finally, create a backup selection.

```
aws backup create-backup-selection \
--backup-plan-id xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx \
--cli-input-json file://backup-selection.json \
--profile poc \
--region us-east-1
```

File: backup-selection.json

```
{
    "BackupSelection": {
	"SelectionName": "efs-0123",
        "IamRoleArn": "arn:aws:iam::xxxxxxxxxxxx:role/service-role/AWSBackupDefaultServiceRole",
        "Resources": [],
        "ListOfTags": [
            {
                "ConditionType": "STRINGEQUALS",
                "ConditionKey": "aws-backup",
                "ConditionValue": "efs-0123"
            }
        ]
    }
}
```