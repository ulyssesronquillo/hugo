---
title: 'gcp ssh issues'
author: ulysses

date: 2021-07-20
slug: gcp-ssh-issues
draft: false
---

There are a few issues that prop up every once in a while with gcloud compute ssh. gcloud compute ssh creates local user at first login. The account password has a default expiration of 90 days. If unable to login, you can try logging in as a different name (even a fictitious name) e.g. superheroes, etc. something unique.

```
gcloud compute ssh username@servername --zone us-central1-c --project project-id --internal-ip
```

Once logged in, you can delete local users with expired passwords or perform other admin tasks.

```
userdel -r username
```

You can also try to run chage to adjust the password expiration.

```
chage -M 180 username ​ (extends expiration from 90 to 180 days)
```

If you continue to have login issues, you can also delete Metadata SSH keys in both the instance and project levels.

Last resort you can use force key overwrite which will regenerate a new key and overwrite broken ssh keys.

```
gcloud compute ssh username@servername \
--force-key-file-overwrite \
--zone us-central1-c \
--project project-id \
--internal-ip
```