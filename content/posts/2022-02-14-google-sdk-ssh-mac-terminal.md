---
title: 'google sdk ssh mac terminal'
author: ulysses

date: 2022-02-14
slug: google-sdk-ssh-mac-terminal
draft: false
---

I’m having trouble logging in using Google SDK Compute SSH on a Mac Terminal.

Here’s the fix.

```
gcloud compute ssh USERNAME@SERVER --zone ZONE --project PROJECTID --internal-ip 2>&1
```

There was an issue with a redirect to another shell.