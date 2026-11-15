---
title: 'aws rotate iam keys'
author: ulysses

date: 2020-07-26
slug: aws-rotate-iam-keys
draft: false
---

Here’s a script that will rotate AWS IAM keys.

```
#!/bin/bash
# set files
user='johndoe'
newkey='/root/new-access-key.json'
oldkey='/root/old-access-key.json'
credentials='/root/.aws/credentials'
# get old credentials
aws iam list-access-keys --user-name $user > $oldkey
okey=$(jq .AccessKeyMetadata[0].AccessKeyId $oldkey | tr -d \")
# create new key
aws iam create-access-key --user-name $user > $newkey
# get new access keys and new secret
nkey=$(jq .AccessKey.AccessKeyId $newkey | tr -d \")
nsecret=$(jq .AccessKey.SecretAccessKey $newkey | tr -d \")
# backup old credentials
cp /root/.aws/credentials /root/.aws/credentials-backup
# store the new key
echo '[default]' > $credentials
echo 'aws_access_key_id = ' $nkey >> $credentials
echo 'aws_secret_access_key = '$nsecret >> $credentials
sleep 10
# delete old key
aws iam delete-access-key --user-name $user --access-key-id $okey
rm $newkey
rm $oldkey
```

The script performs the following:

1. Retrieves the current key
2. Creates a new key
3. Backup the current credentials file
4. Create a new credentials file
5. Deletes the old key
6. Deletes the temp files
7. Done