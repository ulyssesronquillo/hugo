---
title: 'python boto3 s3 list objects'
author: ulysses

date: 2022-02-27
slug: python-boto3-s3-list-objects
draft: false
---

How to list S3 objects using Python Boto3

```
import boto3
from sys import argv
bucket=argv[1]
s3 = boto3.resource('s3')
mybucket = s3.Bucket(bucket)
def list_buckets():
    print("List of Buckets: ")
    for bucket in s3.buckets.all():
        print(bucket.name)
def list_files():
    print("Buckets: The objects in the \"" + bucket + "\" buckets are ... ")
    for files in mybucket.objects.all():
        print(files.key)
def main():
    #list_buckets()
    list_files()
if __name__ == "__main__":
    main()
```

Running command

```
$ python test.py bucket-name    # with python
$ ./test.py bucket-name         # without python
```

Results

```
Buckets: The objects in the "bucket-name" are ....
abc.txt
def.txt
```