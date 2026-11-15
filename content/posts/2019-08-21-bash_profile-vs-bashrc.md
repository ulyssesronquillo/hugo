---
title: '.bash_profile vs .bashrc'
author: ulysses

date: 2019-08-21
slug: bash_profile-vs-bashrc
draft: false
---

.bash\_profile is executed for login shells. .bashrc is executed for interactive non-login shells. When you login, .bash\_profile is executed. If you are already logged in, .bashrc is executed. .bashrc is also executed when you start a new bash using /bin/bash.