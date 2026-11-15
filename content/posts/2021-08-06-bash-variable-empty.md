---
title: 'bash variable empty'
author: ulysses

date: 2021-08-06
slug: bash-variable-empty
draft: false
---

Here’s how to check in Bash if a variable is empty or unset.

```
if [ -z "${VAR}" ]; 
then
  echo 'do something'
else
  echo 'do another'
fi
```

One liner

```
if [ -z "${VAR}" ]; then echo 'do something'; else echo 'do another'; fi
```

The inverse

```
if [ ! -z "${VAR}" ]; 
then
  echo 'do something'
else
  echo 'do another'
fi
```

```
if [ ! -z "${VAR}" ]; then echo 'do something'; else echo 'do another'; fi
```