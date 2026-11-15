---
title: 'gcp list of bms servers'
author: ulysses

date: 2022-09-15
slug: gcp-list-of-bms-servers
draft: false
---

Here’s how to list Bare Metal Servers in Google Cloud Platform via gcloud.

```
gcloud bms instances list --region REGION --project PROJECT
```

Result

```
NAME            ID                 PROJECT         REGION       MACHINE_TYPE           CLIENT_IPS    PRIVATE_IPS                    STATE
server-001      at-xxxxxxx-svr001  project-01      us-central1  o2-ultramem-896-metal  10.0.0.1      192.168.253.1,192.168.252.1    RUNNING
server-002      at-xxxxxxx-svr002  project-02      us-central1  o2-ultramem-896-metal  10.0.0.2      192.168.253.2,192.168.252.2    RUNNING
```

Obviously you can see the same from GCP’s Console.