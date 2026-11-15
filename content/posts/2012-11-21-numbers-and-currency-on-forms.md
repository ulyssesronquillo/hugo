---
title: 'numbers and currency on forms'
author: ulysses

date: 2012-11-21
slug: numbers-and-currency-on-forms
draft: false
---

This article will show you how to limit currency and numbers only in a form. There are essentially two different approaches when validating data. One way is to validate before submitting the form. The other is to validate after submitting the form. Obviously, validating before submit has its own merits. Incorrect data can be corrected before hitting the submit button. In this article, we will validate a field to allow numbers and currency only. We will allow up two decimal places to reflect currency values. The HTML markup is detailed below.

#### HTML Form

We have a simple form with one input and a submit button. There are two Javascript functions in the input field. The blockNonNumbers function allow numbers only to be typed on the input field. Non-number characters are ignored. The extractNumber function formats the input to two decimal places.

```
<form action="" id="login" method="post"> 
<input name="username" onblur="extractNumber(this,2,false);" onkeypress="return blockNonNumbers(this, event, true, false);" onkeyup="extractNumber(this,2,false);" type="text" value=""></input>
</form>#### Javascript
```

I’ve included the [validate.js](http://uly.me/demo/validate.js) Javascript code, which you can download. The code contains two functions: blockNonNumbers and extractNumber. In the markup, we can link to the Javascript file in the head section of the page using the following markup.

```
<script language="javascript" src="validate.js"></script>
```

#### All Together Now

Here’s the entire markup.

```
<script language="javascript" src="validate.js"></script>
<form action="" id="login" method="post">
<input name="username" onblur="extractNumber(this,2,false);" onkeypress="return blockNonNumbers(this, event, true, false);" onkeyup="extractNumber(this,2,false);" type="text" value=""></input> 
</form>
```

[Demo](http://uly.me/demo/numbers.html)
