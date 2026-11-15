---
title: 'remove sensitive info from github'
author: ulysses

date: 2015-06-01
slug: remove-sensitive-info-from-github
draft: false
---

I made a mistake by publishing my database password to an environment file that’s visible. Rookie mistake. Replacing the database password entry with something else and submitting kinda takes care of the problem, but anyone can still view the history of the file and see your password. One way of getting rid of this, if you don’t really care about the history of your submits, is to reinitialize the project back to the initial commit. Here’s how.

```
// Clone the project to your local computer
$ git clone https://github.com/name/myproject.git

// go to your project directory
$ cd myproject

// delete the .git folder where all the history is kept
$ rm -rf .git

// reinitialize your repository
$ git init

// add Github url
$ git remote add origin https://github.com/name/myproject.git

// verify remote
$ git remote -v

// Add all files and commit the changes
$ git add --all
$ git commit -am 'initial commit'

// Finally, push to the origin server which is Github
$ git push -f origin master
```

Your sensitive data is now gone from history. Just be careful next time.