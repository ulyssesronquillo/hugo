---
title: 'bash input executes functions'
author: ulysses

date: 2021-12-01
slug: bash-input-executes-functions
draft: false
---

How to execute functions in Bash based on argument.

There are 2 functions: build and terminate.

```
#!/bin/bash
build () {
 echo 'Building services'
}
terminate () {
 echo 'Terminating services'
}
if [ $1 == 'build' ]; then build
elif [ $1 == 'terminate' ]; then terminate
else echo 'Valid options are "build" or "terminate"'
fi
```

Execute a function based on argument.

```
$ bash test.sh build
Building services

$ bash test.sh terminate
Terminating services

$ bash test.sh anyother
Valid options are "build" or "terminate"
```