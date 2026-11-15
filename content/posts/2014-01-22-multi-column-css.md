---
title: 'multi-column css'
author: ulysses

date: 2014-01-22
slug: multi-column-css
draft: false
---

If you have a long list of words laid out on a page (see list below), it might be better to place them in a multi-column page format. CSS3 makes this entirely possible without using tables or multiple divs. All we need is a single div for the entire list. In this example, we will work with a list of animals. We will use a div class called “animals.”

<div class="animals">aardvark beetle camel dog elephant fox goat hen iguana jackal kangaroo lion</div>To use multi-columns, we simply style the div with:

```
.animals {-moz-column-count:3; -webkit-column-count:3; column-count:3;}
```

Multi-column divs is supported on Firefox, Safari, Chrome and IE browsers.

Multi-Column Example

```
<div style="-moz-column-count: 3; -webkit-column-count: 3; column-count: 3;">
aardvark  
beetle  
camel  
dog  
elephant  
fox  
goat  
hen  
iguana  
jackal  
kangaroo  
lion
</div>
```

Just change the numbers to make multiple columns.