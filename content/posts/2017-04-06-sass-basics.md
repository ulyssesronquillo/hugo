---
title: 'sass basics'
author: ulysses

date: 2017-04-06
slug: sass-basics
draft: false
---

If you use CSS, it can sometimes get repetitive. One way of streamlining your code is to use Sass. Sass is a CSS extension that gives users power and elegance. Sass allows the use of variables, nested rules, mixins, inline imports, and many more in your code by cutting down on some repetitive tasks. Let me show you how it’s done. Below is an example of how to use Sass using variables.

Sass Variables – an example using the same hex color over and over again.

```
$link-color: #054943;
a, a:active { color: $link-color; }
pre { color: $link-color; }
#page { color: $link-color; }
.list { color: $link-color; }
```

With Sass’ preprocessor, the original will output a result like this:

```
a, a:active { color: #054943; }
pre { color: #054943; }
#page { color: #054943; }
.list { color: #054943; }
```

If you need to change the color in the future, you just need to change one line.

To start Using Sass, just issue the command below. Sass will watch input.scss and generate output.css.

```
$ sass input.scss output.css
```

If you use Github for versioning, you may have to ignore a few files, like the Sass cache, the mapping file and the input.scss itself, from showing up on your Github repository. To learn Sass, visit the [website](http://sass-lang.com/) and read the [documentation](http://sass-lang.com/documentation/). To start using Sass, just [install](http://sass-lang.com/install).