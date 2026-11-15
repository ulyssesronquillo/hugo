---
title: 'bash global variables'
author: ulysses

date: 2023-07-27
slug: bash-global-variables
draft: false
---

Just a few things about Bash variables.

Every variable in Bash is global and are accessible anywhere in the script.

They can be used in a function, loop, or conditional statement within the script.

```
# setting a variable
a = "hello"
# printing a variable
echo $a
# using a variable inside a function
hello_function () {
  echo $a
}
# passing a variable to a function
hello_function $a 
```