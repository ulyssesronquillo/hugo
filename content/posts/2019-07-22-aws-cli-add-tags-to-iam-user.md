---
title: 'aws cli add tags to iam user'
author: ulysses

date: 2019-07-22
slug: aws-cli-add-tags-to-iam-user
draft: false
---

How to add tags to an existing IAM user via AWS CLI.

```
aws iam tag-user \
--user-name john.doe \
--tags '{"Key": "Department", "Value": "Accounting"}'
```

Multiple tags.

```
aws iam tag-user \
--user-name john.doe \
--tags '[{"Key": "Department", "Value": "Accounting"},{"Key": "Manager", "Value": "jane.doe"}]'
```