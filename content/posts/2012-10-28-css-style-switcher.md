---
title: 'css style switcher'
author: ulysses

date: 2012-10-28
slug: css-style-switcher
draft: false
---

Years ago, I implemented an [alternative style switcher](http://www.alistapart.com/articles/alternate/) I found at [A List Apart](http://alistapart.com). But, that solution is quite old now. It was published eleven years ago, back in 2001. Now, I’m looking for something a little bit more modern, perhaps a solution that uses JQuery. The idea is to let the readers choose a CSS stylesheet of their liking by simply clicking on a link. So, here’s the finished product. [Demo](http://uly.me/demo/styleswitcher/).

The Stylesheet

I’m using two very simple stylesheets. The default stylsheet is called [style.css](http://uly.me/demo/styleswitcher/style.css). The alternate stylesheet is called [black.css](http://uly.me/demo/styleswitcher/black.css). This code belongs in the head section of the HTML page.

```
<link href="style.css" rel="stylesheet" title="style" type="text/css"></link>
<link href="black.css" rel="alternate stylesheet" title="black" type="text/css"></link>
```

JQuery

We are using [Google’s JQuery CDN](https://developers.google.com/speed/libraries/devguide#jquery) by also linking it from within the head section of the HTML page. The second line is the Javascript code that actually performs the stylesheet switching. You can download the [styleswitcher.js](http://uly.me/demo/styleswitcher/styleswitcher.js) code directly from my website.

```
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>
<script src="styleswitcher.js" type="text/javascript"></script>
```

CSS Switch

We will provide two links where readers can switch stylesheets from default to black and vice versa. The links are standard HTML links and using Javascript’s onclick event.

```
<a href="#" onclick="setActiveStyleSheet('style');return false;">Default</a> |
<a href="#" onclick="setActiveStyleSheet('black');return false;">Black</a>
```

Putting It All Together

Here’s the final code.

```
<title>CSS Switcher</title>
<link href="”style.css”" rel="”stylesheet”" title="”style”" type="”text/css”"></link>
<link href="”black.css”" rel="”alternate" stylesheet="" title="”black”" type="”text/css”"></link>
<script src="”//ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js”"></script>
<script src="”styleswitcher.js”" type="”text/javascript”"></script>
<a false="" href="”#”" onclick="”setActiveStyleSheet(‘style’);return">Default</a> | 
<a false="" href="”#”" onclick="”setActiveStyleSheet(‘black’);return">Black</a>
```
<a title="Subversion Checkout" href="http://uly.me/demo/styleswitcher/" target="_blank">Demo</a>

Happy switching!

