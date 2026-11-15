---
title: 'jq proccessor'
author: ulysses

date: 2017-05-19
slug: jq-proccessor
draft: false
---

The AWS CLI spits out a JSON output after each successful execution. If you need to grab the result, assign it to a variable, and use it for your subsequent scripts, you need some kind of JSON parser. You can use a tool like jq which will process or filter out the result for you. From jq’s [website](https://stedolan.github.io/jq/),

> jq is a tool for processing JSON inputs, applying the given filter to its JSON text inputs and producing the filter’s results as JSON on standard output. The simplest filter is ., which is the identity filter, copying jq’s input to its output unmodified (except for formatting).

In this example, we will use the AWS CLI to give us a list of running EC2 instances. We will then dump the output into a file called output.json. We will then filter out the “InstanceId” by running it through cat and the jq processor. We will then assign the result to a variable called INSTANCE, and then finally use that variable to associate our instance to an Elastic IP Address.

```
aws ec2 describe-instances --filters Name=instance-state-name,Values=running > output.json
INSTANCEID=$(cat output.json | jq '.Reservations[].Instances[] | {InstanceId} | .InstanceId' --raw-output)
aws ec2 associate-address --instance-id $INSTANCEID --public-ip xxx.xxx.xxx.xxx
```

Filtering a nested JSON can be a bit tricky. In this particular case, we are using a filter you’ll find inside the single quote right after the jq command. To remove quotes from our result, I’m using –raw-output switch. Finally, I then associate our instance to an elastic public IP address.

jq is a very handy tool.