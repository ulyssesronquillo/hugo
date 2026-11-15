---
title: 'aws backup vaults'
author: ulysses

date: 2021-03-05
slug: aws-backup-vaults
draft: false
---

Here’s how to list AWS Backup vaults and plans. You can filter the output by specifying a vault.

```
aws backup list-backup-vaults --query "BackupVaultList[?BackupVaultName=='my-vault']" --output json
```

Output: (outputs are redacted for security reasons)

```
[
    {
        "BackupVaultName": "my-vault",
        "BackupVaultArn": "arn:aws:backup:us-east-1:xxxxxxxxxxxx:backup-vault:my-vault",
        "CreationDate": "2019-02-10T11:38:42.556000-05:00",
        "EncryptionKeyArn": "arn:aws:kms:us-east-1:xxxxxxxxxxxx:key/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "CreatorRequestId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "NumberOfRecoveryPoints": 3
    }
]
```

Display the BackupPlanId of a specific backup plan.

```
aws backup list-backup-plans --query "BackupPlansList[?BackupPlanName=='my-backup-plan'].BackupPlanId"
```

Output: (outputs are redacted for security reasons)

```
[
    "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
]
```