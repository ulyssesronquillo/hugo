---
title: 'aws cli iam keys'
author: ulysses

date: 2019-12-20
slug: aws-cli-iam-keys
draft: false
---

Here’s a few commands to create, delete and disable AWS user keys.

List user keys.

```
aws iam list-access-keys --user-name john.doe
```

Create access key. Results are printed on screen in JSON format.

```
aws iam create-access-key --user-name john.doe
```

Disable a key. The real key id is obfuscated.

```
aws iam update-access-key \
--access-key-id ******************** \
--status Inactive \
--user-name john.doe
```

Delete a key. They real key id is obfuscated.

```
aws iam delete-access-key \
--access-key-id ******************** \
--user-name john.doe
```