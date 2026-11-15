---
title: 'backup rotation'
author: ulysses

date: 2015-06-12
slug: backup-rotation
draft: false
---

After another downtime with my service provider, I wasn’t really happy with my backup strategy. Although, I have a backup plan in place, it’s not to the level of detail that I wanted. Back to the drawing board I went. I realized that what I really needed, was to back up my databases and keep copies of the last few days. Prior to that I was just relying on full file system backup and restore. Thankfully, backing up MySQL databases is not that difficult. The following pieces of code is the backup script I have put together to backup each MySQL database, as well rotate the backups and keep 5 days of copies of each database.

```
#! /bin/bash

# where sql files are stored
cd /home/user/mysql

# list all databases and assign to variable
# exclude 3 MySQL default databases (information_schema,performance_schema,mysql)
DATABASES=`mysql -e "SHOW DATABASES;" | grep -Ev "(Database|information_schema|performance_schema|mysql)"`

# loop through all databases
# remove db that's 5 days old
# rotate dbs. rename 1 day older
# perform backup today
for db in $DATABASES; do
  rm -rf $db-4.sql
  mv $db-3.sql $db-4.sql
  mv $db-2.sql $db-3.sql
  mv $db-1.sql $db-2.sql
  mv $db-0.sql $db-1.sql
  mysqldump $db > "$db-0.sql"
done
```

The for loop will execute everything inside it. The backup rotation gives me 5 days of backups of each database. You can schedule the script to run daily with cron. Just a side note. You need to create .my.cnf file in your home directory with your database credentials, so you don’t have to enter your username and password when running it from cron. Also script needs to be executable. A simple chmod +x will do the trick.