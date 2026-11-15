---
author: ulysses
title: 'Bash function within a function'
date: 2023-12-24
slug: bash-function-within-a-function
draft: false
---

How to make a function call within a function in Bash.

In my previous [post]({% post_url 2023-12-20-gcp-restore-boot-disk %}), I used several functions. We will call them in the main function below.

```
main() {

  checkLogin
  displayHeader
  getDisks
  getSnaps 

  read -p "Do you want to proceed with restore? Are you sure? " -n 1 -r
  echo    # (optional) move to a new line
  if [[ $REPLY =~ ^[Yy]$ ]]
  then
    stopServer
    detachDisks
    deleteDisks
    createDisks
    attachDisks
    setAutodelete
    startServer
  fi
}

main 
```
