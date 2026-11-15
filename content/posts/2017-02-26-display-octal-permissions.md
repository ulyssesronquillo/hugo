---
title: 'display octal permissions'
author: ulysses

date: 2017-02-26
slug: display-octal-permissions
draft: false
---

If you’re working on the command line, listing a directory to display permissions of files is not always the most user-friendly. Here’s an example of listing the files in a directory using the ‘ls -al’ command.

```
$ ls -al
total 20
drwxrwsr-x  2 ulysses www-data 4096 Feb 26 13:31 .
drwxrwsr-x 10 ulysses www-data 4096 Feb 26 02:30 ..
-rw-rw-r--  1 ulysses www-data    0 Feb 26 13:31 display.txt
-rwxrwxr-x  1 ulysses ulysses   659 Dec  3 06:40 sync_com.sh
-rw-r--r--  1 ulysses ulysses   181 Feb 26 13:26 sync_db.sh
-rwxrwxr-x  1 ulysses ulysses   244 Feb 26 13:23 sync_s3.sh
```

There has to be a better way to display permissions?

Well, there is. It’s a command called “stat” that displays the detailed status about a file or file system. On one of the switches of the stat command, is an option that allows you to display the file status in human readable format. Here’s an example using the stat from the command line.

```
$ stat -c '%A %a %n' *
664 display.txt
775 sync_com.sh
644 sync_db.sh
775 sync_s3.sh
```

The result is a list of files in a directory with the file permissions in human readable format!