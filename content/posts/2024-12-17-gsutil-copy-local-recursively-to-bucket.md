---
author: ulysses
title: 'gsutil copy local recursively to bucket'
date: 2024-12-17
slug: gsutil-copy-local-recursively-to-bucket
draft: false
---

Here's a gsutil command to copy a directory recursively to a GCS bucket via parallel uploads.

```
# Define source and destination
SOURCE_DIR="/path/to/local/directory"
DEST_BUCKET="gs://your-bucket-name"

# Use gsutil with the -m flag for parallel uploads
gsutil -m cp -r "$SOURCE_DIR" "$DEST_BUCKET"
```
