---
title: 'gcp increase download speed for gsutil'
author: ulysses

date: 2019-10-02
slug: gcp-increase-download-speed-for-gsutil
draft: false
---

If you’re downloading large files, you can speed up download speeds by modifying gsutil. Decrease the number of threads and increase the number of components.

```
gsutil \
-o "GSUtil:parallel_thread_count=1" \
-o "GSUtil:parallel_process_count=8" \
cp gs://bucket/source.dat /download/dest/file.dat
```