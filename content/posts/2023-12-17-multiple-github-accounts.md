---
author: ulysses
title: 'multiple github accounts'
date: 2023-12-17
slug: multiple-github-accounts
draft: false
---

I have two Github accounts. The first one was cloned using HTTPS. When it was time to add a second one, I really didn't want to mess around with multiple Github accounts and dealing with multiple credentials. I've decided to just clone the second account using SSH. I decided to do this mainly to simplify setup and to avoid the headaches with setting up multiple accounts in the config.

- First repo - was cloned using HTTPS
- Second repo - was cloned using SSH

The first repo which uses HTTPS requires a github key which will need to be generated on Github. The first time a repo is cloned, you'll be prompted to supply the key. This key is kept in the **~/.git-credentials** file on the local desktop. The second repo which uses SSH requires a ssh key to be generated locally on your desktop, which you will then need to upload to github to allow authentication. 

So here we go. Two separate ways of cloning repos without stepping on each other.
