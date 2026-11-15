---
title: 'multiple txt dns records'
author: ulysses

date: 2018-06-10
slug: multiple-txt-dns-records
draft: false
---

I recently moved my website hosting from Linode to AWS LightSail. Part of the move was working with Route 53 for DNS, as well as setting up my domain’s email, e.g. the MX record. I’m using ProtonMail for email and they require that I add multiple TXT records. Part of the problem is Route 53 will not allow duplicate TXT records. After a few searches, I learned that you can enter in multiple values in the TXT record as long as you place them on multiple lines. That solved the problem for me.