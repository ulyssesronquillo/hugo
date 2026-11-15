---
title: 'phpmailer and gmail smtp'
author: ulysses

date: 2013-08-22
slug: phpmailer-and-gmail-smtp
draft: false
---

Although PHP comes with its own email() function, it lack features. There’s an alternative called PHPMailer that’s easy to implement. PHPMailer is a library class used by many popular PHP projects. In this article, I’ll show how PHPMailer is used to send out notification emails via GMail’s STMP server. Using GMail SMTP server requires an account as well as the need to authenticate. So, here’s the code using PHPMailer and GMail SMTP server.

```
// email class
require_once('class.phpmailer.php');

$mail             = new PHPMailer();
$mail->IsSMTP(); // telling the class to use SMTP
$mail->Host       = "domain.tld";          // SMTP server
$mail->SMTPAuth   = true;                  // enable SMTP authentication
$mail->SMTPSecure = "tls";                 // sets the prefix to the servier
$mail->Host       = "smtp.gmail.com";      // sets GMAIL as the SMTP server
$mail->Port       = 587;                   // set the SMTP port for the GMAIL server
$mail->Username   = "name@gmail.com";      // GMAIL username
$mail->Password   = "password";            // GMAIL password
$mail->Subject    = "Your Subject";
$mail->Body       = "Your message.";

// recipient      
$address          = "name@domain.tld";
$mail->AddAddress($address, "Your Friend");

// sender
$mail->SetFrom('name@gmail.com', 'Your Name');
$mail->AddReplyTo("name@gmail.com","Your Name");

// send out email
if(!$mail->Send()) {
  echo "Mailer Error: " . $mail->ErrorInfo;
} else {
  echo "Message sent!";
}
```

Include the code in your projects. You can also create a function and call the function each time you need to send out an email notification. Off course, you’ll need to pass variables such as recipients, body message, etc to complete your function.