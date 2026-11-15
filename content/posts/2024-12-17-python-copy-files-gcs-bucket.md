---
author: ulysses
title: 'python copy files gcs bucket'
date: 2024-12-17
slug: python-copy-files-gcs-bucket
draft: false
---

I have a Python script that copies files from a local directory to a GCS bucket and down a couple of directories.

The script was tested in a Python virtual environment. Google Cloud Storage module is required which can be installed via pip.

```
pip install google-cloud-storage
```

If you have trouble running pip, you may have to run this on Linux Mint (Ubuntu) to update the virtual environment.

```
apt install python3.12-venv
```

For authentication, you will need to download the service account credentials key that has write access to the GCS bucket.

```
export GOOGLE_APPLICATION_CREDENTIALS="key.json"
```

Finally, here's the Python script ...


```
#!bin/python

from google.cloud import storage
import os

def upload_files_to_gcs(bucket_name, directory, destination_directory):
    """Uploads files from a local directory to a GCS bucket.

    Args:
        bucket_name: The name of the GCS bucket.
        directory: The local directory containing the files to upload.
        destination_directory: The directory in the GCS bucket where the files will be uploaded.
    """

    storage_client = storage.Client()
    bucket = storage_client.bucket(bucket_name)

    for file_name in os.listdir(directory):
        file_path = os.path.join(directory, file_name)

        if os.path.isfile(file_path):
            blob = bucket.blob(os.path.join(destination_directory, file_name))
            blob.upload_from_filename(file_path)

            print(f"Uploaded {file_name} to {bucket_name}/{destination_directory}")

if __name__ == "__main__":
    bucket_name = "ulysses-test-bucket"
    directory = "/home/ulysses/Code/python/gcs/upload"
    destination_directory = "upload/test/"

    upload_files_to_gcs(bucket_name, directory, destination_directory)
```
