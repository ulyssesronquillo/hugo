---
title: 'git export'
author: ulysses

date: 2012-11-07
slug: git-export
draft: false
---

Subversion has an export command when you want a copy of the repository without the .svn directories and files. Git Export is similar to Subversion’s Export command. To export a project in Git, you will need to go to the root of your Git project and issue the following commands.

```
cd git/project
```

Create a gzip file or a zip file.

```
git archive master | gzip > project.tgz
```

or

```
git archive master | zip > project.zip
```