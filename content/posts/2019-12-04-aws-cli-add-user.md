---
title: 'aws cli add user'
author: ulysses

date: 2019-12-04
slug: aws-cli-add-user
draft: false
---

Here’s how to add an AWS user using the CLI.

```
aws iam create-user --user-name john.doe \
--tags Key='Name',Value='John Doe' Key='Role',Value='Admin'
```

Create an access key for the user.

```
aws iam create-access-key --user-name john.doe
```