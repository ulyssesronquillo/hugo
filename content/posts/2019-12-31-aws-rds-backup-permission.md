---
title: 'aws rds backup permission'
author: ulysses

date: 2019-12-31
slug: aws-rds-backup-permission
draft: false
---

Here’s the IAM policy to allow RDS Backup or create a snapshot on AWS.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "rds:RestoreDBClusterFromSnapshot",
		"rds:DescribeDBSnapshots",
		"rds:CopyDBSnapshot",
		"rds:CopyDBClusterSnapshot",
		"rds:DeleteDBSnapshot",
		"rds:DeleteDBClusterSnapshot",
		"rds:CreateDBSnapshot",
		"rds:RestoreDBInstanceFromDBSnapshot",
		"rds:CreateDBInstance",
		"rds:DescribeDBClusterSnapshots",
		"rds:DescribeDBInstances",
		"rds:DescribeDBClusters",
		"rds:DeleteDBInstance",
		"rds:CreateDBClusterSnapshot",
		"rds:ModifyDBSnapshotAttribute",
		"rds:ModifyDBClusterSnapshotAttribute",
		"rds:ListTagsForResource",
		"rds:DeleteDBCluster",
		"ec2:DescribeSecurityGroups",
		"ec2:DescribeRegions",
		"ec2:DescribeAvailabilityZones",
		"ec2:DescribeVpcs",
		"ec2:DescribeAccountAttributes",
		"ec2:DescribeSubnets",
		"iam:GetUser",
		"iam:GetAccountAuthorizationDetails",
		"kms:ReEncrypt*",
		"kms:GenerateDataKey*",
		"kms:CreateGrant",
		"kms:DescribeKey*",
		"kms:ListKeys",
		"kms:ListAliases",
		"kms:Encrypt",
		"kms:Decrypt",
		"kms:GenerateDataKeyWithoutPlaintext",
		"kms:ListKeys",
		"kms:ListAliases",
		"kms:ListResourceTags"
            ],
            "Resource": "*"
        }
    ]
}
```