---
title: 'set immutable attribute'
author: ulysses

date: 2019-11-27
slug: set-immutable-attribute
draft: false
---

If you don’t want a file edited or deleted, you can set the immutable attribute to ON. If activated, not even root or the owner of the file can delete it. Users with write access can still read it, but they obviously will not be able to modify it. To unset it, just use the -i option.

```
# Set immutable attribute
sudo chattr +i text.txt

# Unset immutable attribute
sudo chattr -i text.txt
```