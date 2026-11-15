---
title: 'remove extended attributes on mac'
author: ulysses

date: 2022-04-03
slug: remove-extended-attributes-on-mac
draft: false
---

If you have a file with @ sign at end, this is how to remove extended attributes on the Mac OS.

Example.

```
ls -l
-rwxr-xr-x@  4 username  staff   128 Mar 24 10:51 sample.txt
```

Remove extended attributes.

```
xattr -c sample.txt
```

Result

```
ls -l
-rwxr-xr-x  4 username  staff   128 Mar 24 10:51 sample.txt
```