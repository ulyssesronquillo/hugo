---
title: 'subversion checkout'
author: ulysses

date: 2012-10-19
slug: subversion-checkout
draft: false
---

The Subversion Checkout command is used to pull out a working copy of a project from the main Subversion repository. The Checkout command signals the start of using version control. This command is usually performed once at the beginning, but sometimes, it can also be performed whenever there are major changes to a project structure. To perform a checkout, type the following command in the Terminal.

```
svn co http://repository/project/trunk .
```

The period at the end is very important.

It tells Subversion that you want a copy of “trunk” in the current directory.
