---
title: 'copy s3 to gcs'
author: ulysses

date: 2021-10-13
slug: copy-s3-to-gcs
draft: false
---

You can use gsutil to copy directly from a S3 bucket to a GCS bucket.

gsutil can read/write to a S3 bucket as long as it has access to your AWS credentials.

The -R option is recursive and -m is for multi-threaded or multi-processing.

```
gsutil -m cp -R s3://bucket/ gs://bucket
```

You can also use rsync instead of cp. Just be aware that rsync does not copy empty directory trees

```
gsutil -m rsync -r s3://bucket/ gs://bucket
```

If you plan to use -d, Use it with caution since it deletes content.

You may have to set the following to your defaults accounts.

```
export AWS_PROFILE=yourprofile
gcloud config set project your-project-id
```

This ensures that default profile and projects are used in both AWS and GCP.