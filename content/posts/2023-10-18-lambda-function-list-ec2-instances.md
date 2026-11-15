---
title: 'lambda function list ec2 instances'
author: ulysses

date: 2023-10-18
slug: lambda-function-list-ec2-instances
draft: false
---

This is a Lambda function code that list EC2 instances from multiple regions and write the output to a S3 bucket.

Include name and IP address on the output.

```
import boto3
import json
import os
from botocore.exceptions import NoCredentialsError

# Set the AWS regions you want to query
regions = ['us-east-1', 'us-west-2', 'eu-west-1']

# Set the S3 bucket and object key for storing the output
s3_bucket = 'your-s3-bucket-name'
s3_object_key = 'ec2-instances-list.txt'

def lambda_handler(event, context):
    ec2_instances = []

    for region in regions:
        try:
            # Create an EC2 client for the specified region
            ec2 = boto3.client('ec2', region_name=region)

            # Describe EC2 instances in the region
            response = ec2.describe_instances()

            for reservation in response['Reservations']:
                for instance in reservation['Instances']:
                    # Extract instance information
                    instance_name = "N/A"
                    instance_ip = "N/A"
                    for tag in instance.get('Tags', []):
                        if tag['Key'] == 'Name':
                            instance_name = tag['Value']
                    if instance.get('PublicIpAddress'):
                        instance_ip = instance['PublicIpAddress']

                    ec2_instances.append(f"Region: {region}, Name: {instance_name}, IP: {instance_ip}")

        except NoCredentialsError:
            return "No AWS credentials found."

    # Store the EC2 instance information in an S3 object
    s3 = boto3.client('s3')
    s3.put_object(Bucket=s3_bucket, Key=s3_object_key, Body='\n'.join(ec2_instances), ContentType='text/plain')

    return {
        "statusCode": 200,
        "body": json.dumps("EC2 instance information has been saved to S3.")
    }
```