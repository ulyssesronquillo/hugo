---
author: ulysses
title: 'gcp restore all disks'
date: 2023-12-20
slug: gcp-restore-all-disks
draft: false
---

Here's my latest script on how to restore all disks of a VM in GCP.

```
#!/bin/bash

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

    disks=$(gcloud compute disks list \
        --filter="users:$instance" \
        --format="value(name)" \
        --project="$project")

    echo "Listing disks for $instance ... "

    for disk in $disks; do

        echo $disk
    
    done

}

getSnaps() {

    echo "Listing snapshots to restore for $instance ... "

    for disk in $disks; do

        snap=$(gcloud compute snapshots list \
            --filter="sourceSnapshotSchedulePolicy~$policy AND sourceDisk~$disk" \
            --format="value(name)" \
            --project="$project" \
            --sort-by="~creationTimestamp" | head -n $snapback | tail -n 1)

        echo "$disk: $snap" 

    done 

}

stopServer() {

    echo "Stopping server ..."

    gcloud compute instances stop $instance \
        --zone="$zone" \
        --project="$project"

}

detachDisks() {

    echo "Detaching disks ..."

    for disk in $disks; do

        gcloud compute instances detach-disk $instance \
            --disk="$disk" \
            --zone="$zone" \
            --project="$project"

    done 

}

deleteDisks() {

    echo "Deleting disks ..."

    for disk in $disks; do

        gcloud compute disks delete $disk \
            --zone="$zone" \
            --project="$project"

    done

}

createDisks() {

    echo "Creating disks ..."

    for disk in $disks; do

        snap=$(gcloud compute snapshots list \
            --filter="sourceDisk~$disk" \
            --format="value(name)" \
            --project="$project" \
            --sort-by="~creationTimestamp" | head -n $snapback | tail -n 1)

        gcloud compute disks create $disk \
            --source-snapshot="$snap" \
            --zone="$zone" \
            --project="$project"

    done

}

attachDisks() {

    echo "Attaching disks ..."

    count=1

    for disk in $disks; do

        if [ $count == 1 ]; then 
            gcloud compute instances attach-disk $instance \
                --disk="$disk" \
                --device-name="$disk" \
                --zone="$zone" \
                --project="$project" \
                --boot
        else 
            gcloud compute instances attach-disk $instance \
                --disk="$disk" \
                --device-name="$disk" \
                --zone="$zone" \
                --project="$project"
        fi

        count=$((count+1))

    done 

}

setAutodelete() {

    echo "Setting autodelete on disks ..."

    for disk in $disks; do

        gcloud compute instances set-disk-auto-delete $instance \
            --auto-delete \
            --disk="$disk" \
            --zone="$zone" \
            --project="$project"

    done 

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
