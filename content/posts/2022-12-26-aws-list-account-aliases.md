---
title: 'aws list account aliases'
author: ulysses

date: 2022-12-26
slug: aws-list-account-aliases
draft: false
---

Here’s how to list account aliases. I have four profiles in my credentials. I’m looping through all four and printing the aliases.

```
#!/bin/bash
file='results-aws-account-aliases.txt'
> $file
declare -a account=("default" "one" "two" "three")
for i in "${account[@]}"
do
    echo '----------------------' >> $file
    echo 'Account: '$i >> $file
    aws iam list-account-aliases \
    --profile $i 
done
```