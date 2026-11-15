---
author: ulysses
title: 'git push script'
date: 2026-04-21
slug: git-push-script
draft: false
---
Here's my new git push script.

```
#!/bin/bash

comment=$1
if [[ -z $comment ]]; then
  echo "Usage: $0 'put your comment here'"
  exit
fi

git add .
git commit -am "$comment"
git push
```

To use the script, simply execute ./gitPush.sh 'put your git comment here'

The script will add, commit and push it to your remote repository.
