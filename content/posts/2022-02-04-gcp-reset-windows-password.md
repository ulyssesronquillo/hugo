---
title: 'gcp reset windows password'
author: ulysses

date: 2022-02-04
slug: gcp-reset-windows-password
draft: false
---

How to reset password of a GCP Compute Engine running on Windows OS.

```
gcloud compute reset-windows-password servername \
--zone us-central1-a \
--project your-project-id
```

Output

```
This command creates an account and sets an initial password for the
user [firstname_lastname] if the account does not already exist.
If the account already exists, resetting the password can cause the
LOSS OF ENCRYPTED DATA secured with the current password, including
files and stored passwords.

For more information, see:
https://cloud.google.com/compute/docs/operating-systems/windows#reset

Would you like to set or reset the password for [firstname_lastname]
(Y/n)?  y

Resetting and retrieving password for [firstname_lastname] on [servername]
Updated [https://www.googleapis.com/compute/v1/projects/your-project-id/zones/us-central1-a/instances/servername].
WARNING: Instance [servername] does not appear to have an external IP
address, so it will not be able to accept external connections.
To add an external IP address to the instance, use
gcloud compute instances add-access-config.
password: xxxxxxxxxxxxxxx
username: firstname_lastname
```