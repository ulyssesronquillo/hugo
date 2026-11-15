---
title: 'aws iam tag user'
author: ulysses

date: 2020-01-15
slug: aws-iam-tag-user
draft: false
---

Here’s how to add tags to an existing user.

```
aws iam tag-user \
--user-name ulysses \
--tags "Key"="dept","Value"="it" "Key"="role","Value"="admin"
```

Tags with identical keys are overwritten. New keys are added.