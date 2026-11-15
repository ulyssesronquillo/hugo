---
title: 'gcp list of projects'
author: ulysses

date: 2021-02-28
slug: gcp-list-of-projects
draft: false
---

Here’s another way to list projects in a shared VPC.

```
gcloud compute shared-vpc list-associated-resources your-shared-host
```

Output:

```
project1  PROJECT
project2  PROJECT
project3  PROJECT
...
```