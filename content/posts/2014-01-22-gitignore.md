---
title: gitignore
author: ulysses

date: 2014-01-22
slug: gitignore
draft: false
---

You can ignore specific files in Git by placing a .gitignore file at the root of your local repository. The files listed in .gitignore will not be tracked by Git. Why would you do this? Well, there are certain OS generated files placed in system folders such as .DS\_Store or Thumbs.db that are not really part of your code.

Create a .gitignore file

```
touch .gitignore
```

Edit the .gitignore file

```
sudo nano .gitignore
```

Add the files you want excluded. You can use wildcards.

```
.DS_Store
Thumbs.db
*.log
```

Commit and Push

```
git commit -m "adding .gitignore file" -a
git push
```

That should do it!