---
title: 'gcp projects list'
author: ulysses

date: 2020-03-26
slug: gcp-projects-list
draft: false
---

Here’s how to get a list of GCP projects.

```
gcloud projects list 
```

Result:

```
PROJECT_ID            NAME     PROJECT_NUMBER
your-project-id-xxxx  servers  xxxxxxxxxxxx
```

Use awk to display the project id only.

```
gcloud projects list | awk '{print $1}'
```

Result

```
PROJECT ID
your-project-id-xxxx
```