---
title: 'subversion tag'
author: ulysses

date: 2012-11-02
slug: subversion-tag
draft: false
---

Subversion Tags are snapshots of a project at a certain time. Tags are ideal for version releases. To create a tag, you will need to type the following command in the Terminal. It’s a good idea when creating a project that you create a tag directory under the project directory. The tag directory will be the place where you can store all your tag releases in an organized way.

```
svn copy http://repository/project/trunk \ 
         http://repository/project/tags/1.0 \ 
         -m "Place comments here."
```