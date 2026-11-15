---
title: 'alternative to jq'
author: ulysses

date: 2023-10-18
slug: alternative-to-jq
draft: false
---

If you don’t have JQ (JSON Parser) installed, you can use a combination of echo, grep and sed to pull out the data.

```
# create new credentials
new_access_keys_json=$(aws iam create-access-key --user-name $user --profile $profile)
new_access_key_id=$(echo "$new_access_keys_json" | grep -o '"AccessKeyId": "[^"]*' | sed 's/"AccessKeyId": "//')
new_access_secret_key=$(echo "$new_access_keys_json" | grep -o '"SecretAccessKey": "[^"]*' | sed 's/"SecretAccessKey": "//')
```

In this example, we are creating new AWS IAM credentials. AccessKeyID and secretKey are extracted from JSON.
