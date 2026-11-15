---
title: 'gcp list of sql instances'
author: ulysses

date: 2021-02-28
slug: gcp-list-of-sql-instances
draft: false
---

Here’s how to list SQL instances within your GCP project.

```
gcloud sql instances list --project your-project-id
```

Output:

```
NAME             DATABASE_VERSION         LOCATION       TIER              PRIMARY_ADDRESS  PRIVATE_ADDRESS  STATUS
database1        SQLSERVER_2017_STANDARD  us-central1-a  db-n1-standard-1  -                10.10.10.11    RUNNABLE
database2        SQLSERVER_2017_STANDARD  us-central1-c  db-n1-standard-1  -                10.10.10.12    RUNNABLE
```