---
author: ulysses
title: 'bash input options'
date: 2023-12-27
slug: bash-input-options
draft: false
---

Here are input options that you can use in Bash.

1. You can set variables within the script.
2. You can pass the arguments via command line.
3. You can prompt the user to input data.

Or you create a script that incorporates all three. 

1. Remove comments if you want to set the variables in the script.
2. Pass arguments via command line using the format provided.
3. Or be prompted to enter all your arguments one at a time.

```
# project="projectid"
# instance="hostname"
# zone="us-central1-c"
# policy="hourly"
# snapback=3

# Format (requires all 5 arguments): ./script.sh project host zone policy snapback
# If no arguments are provided or less than 5 arguments, you will be prompted to enter your options.

if [ -z "$project" ] || [ -z "$instance" ] || [ -z "$zone" ] || [ -z "$policy" ] || [ -z "$snapback" ]; then
    if  [ "$#" -eq 5 ]; then
        project=$1
        instance=$2
        zone=$3
        policy=$4
        snapback=$5
    else 
        read -p "projectId : " project
        read -p "instance  : " instance
        read -p "zone      : " zone
        read -p "policy    : " policy
        read -p "snapback  : " snapback
    fi
fi
echo $project $instance $zone $policy $snapback
```
