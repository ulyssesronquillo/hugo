---
title: 'remove duplicate in a file'
author: ulysses

date: 2018-09-14
slug: remove-duplicate-in-a-file
draft: false
---

Here’s a Perl script for removing duplicates in a file.

```
perl -ne 'print unless $dup{$_}++;' input_file > output_file
```