---
title: 'efs infrequent access'
author: ulysses

date: 2020-10-04
slug: efs-infrequent-access
draft: false
---

Just like in S3, you can have to up to 92% in savings if you use Infrequent Access or IA with AWS EFS (Elastic File Storage). You can create a lifecycle policy to move data from standard storage to infrequent access. Files that are not being used after x number of days are then moved to Infrequent Access. The downside is, the data in IA do not count towards gaining burst credits. You will need to keep a certain amount of standard storage to prevent depleting your burst credits.

```
aws efs put-lifecycle-configuration \
--file-system-id fs-xxxxxxxx \
--lifecycle-policies TransitionToIA=AFTER_30_DAYS \
--region us-east-1
```