---
title: 'domain sorter'
author: ulysses

date: 2018-09-14
slug: domain-sorter
draft: false
---

Here’s a Bash and Perl script for sorting domains and subdomains.

Command:

```
$ cat filename | perl -ple'$_=join".",reverse split/\./' | sort | perl -ple'$_=join".",reverse split/\./'
```

What’s in the domains.txt?

```
$ cat domains.txt
domain.com
abc.com
xyz.com
bbb.com
mail.gmail.com
ess.sfss.org
csub.edu
gmail.com
```

Result:

```
$ cat domains.txt | perl -ple'$_=join".",reverse split/\./' | sort | perl -ple'$_=join".",reverse split/\./'
abc.com
bbb.com
domain.com
gmail.com
mail.gmail.com
xyz.com
csub.edu
ess.sfss.org
```

You can also pipe the result to another file.

```
$ cat filename | perl -ple'$_=join".",reverse split/\./' | sort | perl -ple'$_=join".",reverse split/\./' > output.txt
```

[Source](https://www.perlmonks.org/?node_id=299555).