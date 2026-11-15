---
title: 'logging in to aws and gcp'
author: ulysses

date: 2023-01-22
slug: logging-in-to-aws-and-gcp
draft: false
---

Here’s my Bash script to login to both AWS and GCP. It has a little bit of intelligence. It checks if you are already logged in, and skips if you are. If not logged in, it will open up the cloud web console which is protected by Okta. The script has been redacted and replace with generic usernames and web pages for security reasons.

```
#!/bin/bash
## CHECK IF LOGGED IN TO GCP 
read -p "Login to GCP? (y/n) : " login_gcp
if [[ $login_gcp = "y" ]]; then
  file1="/Users/username/code/etc/auth-gcp.txt"
  gcloud auth print-identity-token 1> /dev/null 2> $file
  user=$(gcloud config list account --format "value(core.account)")
  auth=$(cat "$file" | head -n 1)
  rm -f $file1
  if [[ $auth == "Reauthentication required." ]] ||  [[ $user != "first.last@domain.com" ]]; then
    echo "Logging in to Google Cloud Platform."
    gcloud auth login
    gcloud auth application-default login
    open https://okta-login
  else
    echo "You are already logged in to Google Cloud Platform."
  fi
else
  echo "Skipping GCP ... "
fi
## CHECK IF LOGGED IN TO AWS
read -p "Login to AWS? (y/n) : " login_aws
if [[ $login_aws = "y" ]]; then  
  file2=""/Users/username/code/etc/auth-aws.txt""
  aws sts get-caller-identity 2> $file2
  expired=$(tail -n +2 "$file2")
  rm -f $file2
  if [[ $expired =~ "expired" ]] || [[ $expired =~ "Unable" ]]; then
    open https://okta-login
    echo "please wait until web page loads ... "
    read -p "Press any key to continue... " -n1 -s
    echo ""
    basecred='/Users/username/.aws/credentials.base'
    newcreds='/Users/username/Downloads/credentials'
    creds='/Users/username/.aws/credentials'
    if [ ! -f $newcreds ]; then
      echo 'No AWS credentials.'
      exit
    else
      cat $newcreds $basecred > $creds
      echo 'New AWS credentials.'
      sleep 3
      rm -f $newcreds
    fi
  else
    echo "You are already logged in to AWS."
  fi
else 
  echo "Skipping AWS ... "
fi
```