---
author: ulysses
title: 'scp multiple files'
date: 2024-01-09
slug: scp-multiple-files
draft: false
---

scp is an excellent utility for copying files to and from a server without the need for running a ftp server or some sort of file transfer service on the server. scp uses your existing ssh access to copy files to and from a server. You will need permissions to the remote server otherwise scp copy will fail. Whether pulling down a file or pushing a file to a server, scp can be invoked from a client regardless of file direction. You can copy a single file or multiple files. The examples below demonstrate this.

scp copy a single file to a server.

``` 
scp file.ext username@server:/home/homedir/
``` 

scp copy multiple local files to a server.

``` 
scp file1.ext file2.ext file3.ext username@server:/home/homedir/
```

scp copy a single file from a server to the desktop.

```
scp username@server:/home/homedir/file.ext .
```

scp copy multiple files from a server to the desktop.

``` 
scp username@server:/home/homedir/*.{txt,doc} . 
```

Here's a script that I wrote to upload multiple files to a server. It looks for text and php files in the current directory and then uploads them to the server.

```
#!/bin/bash
# create temp file
temp="temp"
>$temp
# loop through selected files in the current directory
for file in *.{txt,php}; do
    # put all files in one row
    echo -n "$file " >> $temp 
done
# add new line at the end
echo "" >> $temp
# assign the list to a variable called $files
files=$(cat $temp)
# scp the files to the cloudreporting server
scp $files username@server:/home/homedir
# delete temp file
rm -f $temp
```

