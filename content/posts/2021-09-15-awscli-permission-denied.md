---
title: 'awscli permission denied'
author: ulysses

date: 2021-09-15
slug: awscli-permission-denied
draft: false
---

When running awscli as a user, I’m getting a permissioned denied.

```
[user@servername ~]$ aws s3 ls
Traceback (most recent call last):
  File "/home/db2inst1/.local/bin/aws", line 19, in <module>
    import awscli.clidriver
  File "/home/db2inst1/.local/lib/python2.7/site-packages/awscli/clidriver.py", line 17, in <module>
    import botocore.session
  File "/home/db2inst1/.local/lib/python2.7/site-packages/botocore/session.py", line 26, in <module>
    import botocore.configloader
  File "/home/db2inst1/.local/lib/python2.7/site-packages/botocore/configloader.py", line 19, in <module>
    from botocore.compat import six
  File "/home/db2inst1/.local/lib/python2.7/site-packages/botocore/compat.py", line 172, in <module>
    import xml.etree.cElementTree
  File "/usr/lib64/python2.7/xml/etree/cElementTree.py", line 3, in <module>
    from _elementtree import *
ImportError: PyCapsule_Import could not import module "pyexpat"
</module></module></module></module></module></module>
```

This is a permission error with the directory where the awscli is installed.

```
$ which aws 
/usr/local/bin/aws
```

I ran chmod to fix the directory permission.

```
chmod -R 755 /usr/local/aws-cli/
```

The error is now gone.

```
$ aws s3 ls
bucket-1
bucket-2
bucket-3
```