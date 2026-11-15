---
title: 'remove commas from forms'
author: ulysses

date: 2012-11-16
slug: remove-commas-from-forms
draft: false
---

This article will show you how to remove commas, semicolons, or any character, from a form. This tidy PHP script is quite useful when filtering out unwanted characters submitted in a form. This is important when the data is collected and exported later to a CSV (comma-delimited values) file. CSV files use commas and semicolons to separate data values. Having commas and semicolons in your data creates confusion and unwanted results. This neat PHP script removes commas and semicolons, and replaces them with a blank value.

#### HTML Form

First, the HTML form. This is just a HTML form with one field and a submit button. The form calls itself when submitted since the “action” field is left blank.

```
<form action="" method="post"> <input name="field"></input> <input name="submit" type="submit"></input> </form>#### PHP
```

Now, the fun part. I came up with a list of characters that I want filtered out. In this example, I want to filter out commas and semicolons only. The unwanted characters are placed in an array. I cleaned up the input data using a PHP function called str\_replace(). This PHP function replaces commas and semicolons with blanks. Finally, the results are assigned to a variable called $clean and echoed to the screen.

```
$list = array(",", ";");
$clean = str_replace($list, "", $_POST['field']);
echo $clean;
```

#### PHP Function

Taking one more step. I made the code modular by creating a function called clean\_input(). I can then invoke the function numerous times on my script without repeating code. I simply call the clean\_input() function when I need it. The function uses the same code above with some slight modification. We are passing the $in variable to the function. This is going to be in input field on our form. The clean\_input function replaces it, and the results are returned.

```
function clean_input($in) {
  $list = array(",", ";");
  $clean = str_replace($list, "", $in);
  return $clean;
}
$output = clean_input($_POST['field']);
echo $output;
```

#### All Together Now

Finally, we can put all the pieces together in a single file called form.php. The input value in the form will be echoed after submission. Commas and semicolons are filtered out by our PHP function. We can test the function in the demo below. Just type any value to our input field. If you type a comma or semicolon, the input is replaced with a blank.

```
<form action="" method="post"> <input name="field"></input> <input name="submit" type="submit"></input> </form> <?php function clean_input($in) {
  $list = array(",", ";");
  $clean = str_replace($list, "", $in);
  return $clean;
}
$output = clean_input($_POST['field']);
echo $output;
/* end of file */
```

[Demo](http://uly.me/demo/commas.php)