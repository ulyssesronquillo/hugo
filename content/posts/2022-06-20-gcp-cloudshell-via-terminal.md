---
title: 'gcp cloudshell via terminal'
author: ulysses

date: 2022-06-20
slug: gcp-cloudshell-via-terminal
draft: false
---

Connect to your CloudShell environment from your terminal.

```
$ gcloud cloud-shell ssh
Welcome to Cloud Shell! Type "help" to get started.
first.last@cloudshell $
first.last@cloudshell $
```

Once logged in, you can set your project.

```
first.last@cloudshell $ gcloud config set project $PROJECT_ID
```