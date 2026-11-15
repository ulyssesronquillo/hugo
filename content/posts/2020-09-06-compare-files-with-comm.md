---
title: 'compare files with comm'
author: ulysses

date: 2020-09-06
slug: compare-files-with-comm
draft: false
---

Here’s a command that will compare two files and display the only entries in the first file that are missing in the second file. To do this, there’s a compare command in Linux Bash called comm that comes with several options. The option we are interested in is the comm -23 which exactly does that. Let me demonstrate.

Let’s say file a.txt contains:

```
one
two
three
four
five
six
seven
eight
nine
ten
```

And file b.txt contains:

```
one
three
four
five
nine
```

We then run comm command using the option -23.

```
comm -23 a.txt b.txt > c.txt
```

 The contents of c.txt is:

```
two
six
seven
eight
ten
```