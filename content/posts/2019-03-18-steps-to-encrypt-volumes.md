---
title: 'steps to encrypt volumes'
author: ulysses

date: 2019-03-18
slug: steps-to-encrypt-volumes
draft: false
---

Here the steps to encrypt an unencrypted volume.

1. Take a snapshot of the unencrypted volume.
2. Make a copy of that snapshot and turn on encryption.
3. Create a volume of the encrypted snapshot.
4. Stop the instance.
5. Detach the original unencrypted volume from the instance.
6. Attach the newly created encrypted volume to the instance.
7. Start the instance.

AWS CLI

```
# CREATE A SNAPSHOT
aws ec2 create-snapshot \
--volume-id vol-1234567890abcdef0 \
--description "This is my snapshot"

# COPY SNAPSHOT
aws ec2 copy-snapshot \
--source-region us-west-2 --source-snapshot-id snap-066877671789bd71b \
--region us-east-1 --description "This is my copied snapshot."

# CREATE A VOLUME
aws ec2 create-volume \
--region us-east-1 --availability-zone us-east-1a \
--snapshot-id snap-066877671789bd71b --volume-type io1 --iops 1000

# STOP AN INSTANCE
aws ec2 stop-instances --instance-ids i-1234567890abcdef0

# DETACH A VOLUME
aws ec2 detach-volume --volume-id vol-1234567890abcdef0

# ATTACH A VOLUME
aws ec2 attach-volume --volume-id vol-1234567890abcdef0 \
--instance-id i-01474ef662b89480 --device /dev/sdf

# START AN INSTANCE
aws ec2 start-instances --instance-ids i-1234567890abcdef0
```