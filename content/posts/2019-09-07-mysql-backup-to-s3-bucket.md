---
title: 'mysql backup to s3 bucket'
author: ulysses

date: 2019-09-07
slug: mysql-backup-to-s3-bucket
draft: false
---

Here’s my MySQL backup script to the S3 Bucket.

Just a couple of things about the script. It’s using …

1. AWS CLI
2. Mysqldump

They must be setup and configured to work properly.

```
#!/bin/bash
cd /root/database
TIMESTAMP=$(date +%Y-%m-%d)
S3FILE="s3://bucketname/sqlbackup/backup-$TIMESTAMP.sql"
/usr/bin/mysqldump dbname > dbname.sql
/usr/local/bin/aws s3 cp dbname.sql $S3FILE
sleep 3s
rm dbname.sql
```

Finally, set the S3 bucket with a 7 day retention. Backups older than 7 days are automatically deleted.