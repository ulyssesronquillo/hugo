---
title: fallocate
author: ulysses

date: 2023-08-14
slug: fallocate
draft: false
---

If you want to create dummy files, there’s a faster command than ‘dd’ called ‘fallocate.’

Create a 30GB called temp\_30GB\_file.

```
fallocate -l 30G temp_30GB_file
```

Unlike dd which can take minutes depending on file size, fallocate is instantaneous.