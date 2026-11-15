---
title: 'setup new repository on github'
author: ulysses

date: 2015-02-02
slug: setup-new-repository-on-github
draft: false
---

The following instructions will create a new repository on GitHub. These instructions will assume that you’re logged in to GitHub.com. You can create a new repository by clicking on the link called “create a new repository” found on several pages on GitHub. You can also go directly to this URL: <https://github.com/new>.

You need to provide a repository name that’s hopefully short and memorable. Click the “Create Repository” button to start the initiation process. Once the repository is created, you can create a new local repository on your computer and sync it to GitHub repository.

On your computer:

```
echo "# RepositoryName" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ulyssesr/RepositoryName.git
git push -u origin master
```

If you have an existing local repository, you can push it to GitHub.

```
git remote add origin https://github.com/ulyssesr/RepositoryName.git
git push -u origin master
```