---
title: 'fighting spam with akismet'
author: ulysses

date: 2014-02-06
slug: fighting-spam-with-akismet
draft: false
---

Akismet is a web service that detects spam. Akismet was originally created by Automattic, the company behind WordPress, to filter out spam comments on its own blogs. The use of Akismet has spread to other blogs and CMS engines. Akismet can also be implemented on other websites. There are a number of plugins and libraries available. Akismit also has an API.

Akismet is open-source and free for personal use. Akismet offers professional and enterprise plans for a modest fee. To start using Akismet on your website, you first need an Akismet key which you can get from WordPress.com. Just register. A key will be automatically generated for you. In addition, you also need to download the Akismet class library which you’ll need to include in your web projects.

How to use Akismet

In this example, we will use Akismet’s PHP class library. [Download](https://code.google.com/p/akismet-php4/downloads/list). So, let’s assume you have a comment form or a contact page on your website. When your form is submitted, Akismet will check if the comment is spam or not. The API accesses the Akismet servers and it will return either a yes or a no. Simple enough. How Akismet filters out the spam is not known. They say it’s in the “secret sauce.”

Our HTML Form

We will keep our form simple. We will use the post method. Our form will call itself after submission. We are taking the proper precautions to avoid cross-site scripting attacks, etc. by using the htmlspecialchars function and the $\_SERVER\[“PHP\_SELF”\] variable itself.

```
<form action="<?php echo htmlspecialchars($_SERVER[" method="post" php_self="">
  Name: <input name="name" type="text"></input>
  Email: <input name="email" type="text"></input>
  URL: <input name="url" type="text"></input>
  Comment: <textarea cols="80" name="comment" rows="5"></textarea>
  <input name="submit" type="submit" value="Submit"></input>
</form>
```

Our PHP Code

This is the PHP code that we can place at top of our page. The code will start a new session. It will check if the form is submitted. We will then create a new Akismet object and check if our comment data is spam or not. The Akismet class will contact the Akismet servers. It will determine if our comment is spam or not. If it is, it will mark it as spam. We can either ignore it or save it to the database. If it’s a good comment, we definitely need to keep it and mark it as good comment.

```
<?php // start a new session
session_start();

// our submitted values are sanitized
$author = addslashes(htmlspecialchars(strip_tags(trim($_POST['name']))));
$email = addslashes(htmlspecialchars(strip_tags(trim($_POST['email']))));
$url = addslashes(htmlspecialchars(strip_tags(trim($_POST['url']))));
$comment = addslashes(htmlspecialchars(strip_tags(trim($_POST['comment']))));

// Load array with comment data.
$data = array(
  'author' =?> $author,
  'email' => $email,
  'website' => 'http://www.yourdomain.com/',
  'body' => $comment,
  'permalink' => 'http://www.yourdomain.com/path-to-your-comment-page',
);

// include Akismet class
include "akismet.class.php";

// check if the form was submitted
if(isset($_POST['submit'])) {
  // submitted
  // create a new object
  $akismet = new Akismet('http://www.yourdomain.com/', 'YOUR_WORDPRESS_API_KEY', $data);  

  if($akismet->errorsExist()) {
    echo "Oops! Problem connecting to the Akismet server!";
  } else {
    if($akismet->isSpam()) {
      echo "This is spam!";
      // mark comment as spam
      // option to either save to database or ignore
    } else {
      echo "This is good ham! Let's keep it!";
      // mark comment as good ham
      // definitely save the good comment to the database
    }
  }
}
?>
```

Making a Correction

Occasionally, not very often, Akismet screws up, and marks a good comment as spam, and vice versa. We can tell Akismet, “Hey, what’s the matter! Please correct these comments!” We can correct Akismet by running these two methods.

```
// Submit as Ham
$akismet->submitHam();

// Submit as Spam
$akismet->submitSpam();
```

That’s how how Akismet is implemented in a nutshell.