---
author: ulysses
title: 'gcp check login'
date: 2024-01-22
slug: gcp-check-login
draft: false
---

If you are running a gcloud commands, it will be good to know if a user is still logged in. In some corporate settings, authentication is set to time out after a number of hours. The following lines of code checks if a user is still loggedin and displays a message to reauthenticate if logged out. In reality the script runs a list of GCP projects, but limits the output to just one line. The output is sent to a file. If the first line is equal to "Reauthentication required.", then there's a message telling the user to login again.  If the first line has an error, it means the user is not logged in. It also tells the user to login again. Here's the code.

```
checkLogin() {

    gcloud projects list --format="value[](name)" --limit 1 > reauth.txt 2>&1
    ok=$(cat reauth.txt | head -n 1)
    
    if [[ "$ok" == "Reauthentication required." ]]; then 
        echo "You're not logged in to Google SDK. Please login, then try again."
        exit
    elif [[ "$ok" =~ "ERROR" ]]; then
        echo "You're not logged in to Google SDK. Please login, then try again."
        exit
    fi

    rm -f reauth.txt

}
```

Just call it at the top of the script.

```
checkLogin
```

