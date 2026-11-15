---
title: 'bash aliases'
author: ulysses

date: 2021-07-17
slug: bash-aliases
draft: false
---

Create an alias.

```
alias gcloud='docker run --rm -ti --volumes-from gcloud-config google/cloud-sdk:latest gcloud'
```

Remove an alias.

```
unalias gcloud
```