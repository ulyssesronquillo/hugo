---
title: 'bash variables'
author: ulysses

date: 2020-06-27
slug: bash-variables
draft: false
---

Here’s how to read Bash variables from another file.

Contents of config.sh

```
#!/bin/bash
var1='thisisvariableone'
var2='thisisvariabletwo'
```

Call config.sh from another script.

```
#!/bin/bash
source config.sh
echo var1
echo var2
```

This is extremely helpful if you have multiple scripts using a common variable. You just to update one file instead of multiple files. All the other scripts will read and pick up the same variables from a config file. You can use this to setup your global variables.