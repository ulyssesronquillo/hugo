---
title: 'aws set profile'
author: ulysses

date: 2021-11-07
slug: aws-set-profile
draft: false
---

If you find yourself using a named profile for every awscli command, you can set it temporarily.

Listing a bucket with a named profile.

```
aws s3 ls --profile=yourprofile
```

If you set AWS\_PROFILE, you can then list a bucket without a named profile.

```
export AWS_PROFILE=yourprofile
aws s3 ls
```

After you are done, you can reset it back to default.

```
export AWS_PROFILE=default
```