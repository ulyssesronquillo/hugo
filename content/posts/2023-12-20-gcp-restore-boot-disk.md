---
author: ulysses
title: 'gcp restore boot disk'
date: 2023-12-20
slug: gcp-restore-boot-disk
draft: false
---

Here's my latest script to restore the boot disk of a VM in GCP.

```
#!/bin/bash

# project="projectid"
# instance="hostname"
# zone="us-central1-c"
# policy="hourly"
# snapback=3

# Format (requires all 5 arguments): ./script.sh project host zone policy snapback
# If no arguments are provided or if less than 5 arguments, then you will be prompted to enter options.

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

checkLogin() {

    user=$(gcloud config list account --format "value(core.account)")
    user=$(echo $user | cut -d@ -f1)
    user=${user/./-}

    if [ -z "$user" ]; then
        echo "You're not logged in to Google SDK."
        exit
    fi

}

displayHeader() {

    echo "######################################################"
    echo "Starting the restore process for $instance "
    echo "######################################################"

}

getDisks() {

    disks=$(gcloud compute instances describe $instance \
        --project="$project" \
        --zone="$zone" \
        --format="get(disks[0].source)")

    echo "Listing disks for $instance ... "

    disk=$(echo ${disks##*/})

    echo $disk

}

getSnaps() {

    echo "Listing snapshots to restore for $instance ... "
 
    snap=$(gcloud compute snapshots list \
        --filter="sourceSnapshotSchedulePolicy~$policy AND sourceDisk~$disk" \
        --format="value(name)" \
        --project="$project" \
        --sort-by="~creationTimestamp" | head -n $snapback | tail -n 1)

    echo "$disk: $snap" 

}

stopServer() {

    echo "Stopping server ..."

    gcloud compute instances stop $instance \
        --zone="$zone" \
        --project="$project"

}

detachDisks() {

    echo "Detaching disks ..."

    gcloud compute instances detach-disk $instance \
        --disk="$disk" \
        --zone="$zone" \
        --project="$project"

}

deleteDisks() {

    echo "Deleting disks ..."

    gcloud compute disks delete $disk \
        --zone="$zone" \
        --project="$project"

}

createDisks() {

    echo "Creating disks ..."

    snap=$(gcloud compute snapshots list \
        --filter="sourceDisk~$disk" \
        --format="value(name)" \
        --project="$project" \
        --sort-by="~creationTimestamp" | head -n $snapback | tail -n 1)

    gcloud compute disks create $disk \
        --source-snapshot="$snap" \
        --zone="$zone" \
        --project="$project"

}

attachDisks() {

    echo "Attaching disks ..."

    gcloud compute instances attach-disk $instance \
        --disk="$disk" \
        --device-name="$disk" \
        --zone="$zone" \
        --project="$project" \
        --boot

}

setAutodelete() {

    echo "Setting autodelete on disks ..."

    gcloud compute instances set-disk-auto-delete $instance \
        --auto-delete \
        --disk="$disk" \
        --zone="$zone" \
        --project="$project"

}

startServer() {

    echo "Starting server ..."

    gcloud compute instances start $instance \
        --zone="$zone" \
        --project="$project"

}

main() {

    checkLogin
    displayHeader
    getDisks
    getSnaps 

    read -p "Do you want to proceed with restore? Are you sure? " -n 1 -r
    echo    # (optional) move to a new line
    if [[ $REPLY =~ ^[Yy]$ ]]
    then
        stopServer
        detachDisks
        deleteDisks
        createDisks
        attachDisks
        setAutodelete
        startServer
    fi
    
}

main
```
