---
title: 'continuous order list'
author: ulysses

date: 2014-12-26
slug: continuous-order-list
draft: false
---

Take a look at this [piece of code](http://codepen.io/xmark/pen/ZYpvEv) from Codepen. It’s just a simple ordering list, but the list is broken up into several sections. The numerical order continuous as it spills over to other sections. It even changes to Roman numbering in the last section. How is this possible?

Just HTML and CSS. No Javascript. The key is adding the appropriate CSS to the **ol** markup.

Just look at the examples below.

```
// Start the list at number 6
<ol start="6">
</ol>
```

```
// Start the list at number 11. Assign "roman" class to it.
<ol class="roman" start="11">
</ol>
```

The CSS for “roman” is:

```
.roman { list-style-type:upper-roman; }
```

Pretty neat.