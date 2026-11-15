---
title: 'unsaved changes on forms'
author: ulysses

date: 2012-11-20
slug: unsaved-changes-on-forms
draft: false
---

If you try to abandon a form, you’ll be reminded that you’ve made changes. In addition, a pop up message will come up, asking you whether to stay on the page or to abandon it. This feature is made possible using a Javascript function. This short article will show how to alert users if they made changes to a form, prior to canceling or going to another link.

#### The Form

In this example, I created a simple form with one input called “username.” I’ve added “onchange=’needToConfirm=True'” to monitor the input field. I also added a save and cancel button, as well as an internal link for testing the form later. The save button calls the “needToConfirm” function when the save button is clicked. The cancel button simply reloads the same page when the cancel button is clicked. Here’s the HTML markup.

```
<form action="" id="login" method="post"> <input name="username" onchange="needToConfirm=true" size="40" type="text" value=""></input>  
<input name="save" onclick="needToConfirm=false;" type="Submit" value="Save"></input>
<input onclick="window.location='confirm.html'" type="button" value="Cancel"></input> [Link](confirm.html)#### Javascript
</form>
```

The unsaved changes feature is made possible using Javascript. The function starts out setting needToConfirm to false. A pop up window comes up notifying the user that they have unsaved changes on the form. The user is prompted whether to stay on the page or to leave the page. Add the following Javascript code at the end of the form. Go ahead, test the demo below.

```
<script>
needToConfirm = false;
window.onbeforeunload = askConfirm;
function askConfirm() 
{
 if (needToConfirm) 
 {
 return "You have unsaved changes.";
 }       
}
</script>
```

[Demo](http://uly.me/demo/confirm.html)