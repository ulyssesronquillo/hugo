---
title: 'cloning a gcp repo'
author: ulysses

date: 2018-08-03
slug: cloning-a-gcp-repo
draft: false
---

Here are the steps on how to clone a Google Cloud Platform (GCP) repository. This is assuming you already installed Google Cloud SDK.

```
gcloud init
gcloud source repos clone name_of_repo --project=project_name
cd name_of_repo
git commit -a -m "your comment"
git push -u origin master
```