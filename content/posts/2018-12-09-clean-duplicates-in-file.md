---
title: 'clean duplicates in file'
author: ulysses

date: 2018-12-09
slug: clean-duplicates-in-file
draft: false
---

Here’s a nice command to get rid of line duplicates in a file. I’m sending the output to a temporary file then renaming it back to the original file.

The reason is, it’s probably not a good idea to overwrite a file that you are editing. It’s much safer to send the output to another file.

```
$ awk '!seen[$0]++' filename.txt > filename.temp
$ mv filename.temp filename.txt
```

A much cleaner approach is to use this. It will edit the file in place.

```
awk -i inplace '!seen[$0]++' filename.txt
```