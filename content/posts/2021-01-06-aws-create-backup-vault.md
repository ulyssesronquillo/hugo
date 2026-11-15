---
title: 'aws create backup vault'
author: ulysses

date: 2021-01-06
slug: aws-create-backup-vault
draft: false
---

Here’s how to create a backup vault in AWS Backup.

```
aws backup create-backup-vault --backup-vault-name my-efs-vault --profile default --region us-east-1
```

To delete a vault, run this command.

```
aws backup delete-backup-vault --backup-vault-name my-efs-vault --profile default --region us-east-1
```