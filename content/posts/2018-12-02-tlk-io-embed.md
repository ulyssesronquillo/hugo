---
title: 'tlk.io embed'
author: ulysses

date: 2018-12-02
slug: tlk-io-embed
draft: false
---

tlk.io is a simple chat page that you can embed on your site. If all you are seeing is a blank screen, I may have a fix for it. I don’t think it’s documented anywhere. I did not see it on tlk.io’s website. Here’s the code that they want you to embed. Of course, you have to use your own data-channel instead of the default “hey.”

```
<div data-channel="hey" id="tlkio" style="width:100%;height:400px;"></div>
<script async="" src="http://tlk.io/embed.js" type="text/javascript"></script>
```

The above code will not work if your site is secured via SSL. You’ll need to change the embed.js reference to https. In this case, it would be something like this.

```
<div data-channel="hey" id="tlkio" style="width:100%;height:400px;"></div>
<script async="" src="https://tlk.io/embed.js" type="text/javascript"></script>
```

The code will work in WordPress as well.