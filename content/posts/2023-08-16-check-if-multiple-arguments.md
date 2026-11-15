---
title: 'check if multiple arguments'
author: ulysses

date: 2023-08-16
slug: check-if-multiple-arguments
draft: false
---

If your Bash script calls for 3 arguments, here’s how to check it.

```
if [ "$#" -ne 3 ]
then
  echo "Usage: ./script.sh project diskname policy"
  exit
fi
```

You can adjust -ne 3 to any number based on the number of required arguments.