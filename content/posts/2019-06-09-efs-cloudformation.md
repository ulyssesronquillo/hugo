---
title: 'efs cloudformation'
author: ulysses

date: 2019-06-09
slug: efs-cloudformation
draft: false
---

Here’s a simple EFS CloudFormation template with a one mount target.

```
{
	"AWSTemplateFormatVersion": "2010-09-09",
	"Description": "EFS example setup",
	"Parameters": {
		"VPC": {
			"Description": "VPC ID",
			"Type": "AWS::EC2::VPC::Id"
		},
		"Subnet": {			
			"Description": "Subnet ID",
			"Type": "AWS::EC2::Subnet::Id"
		},
		"EC2SecurityGroup": {
			"Description": "Security Group for EC2 instance",
			"Type": "AWS::EC2::SecurityGroup::Id"
		}	
	},
	"Resources": {
		"EFSFileSystem": {
			"Type" : "AWS::EFS::FileSystem",
			"Properties" : {
				"FileSystemTags" : [
					{"Key" : "Name", "Value" : {"Ref": "AWS::StackName"}}
				]
			}
		},
		"EFSMountTarget": {
			"Type": "AWS::EFS::MountTarget",
			"Properties": {
				"FileSystemId": {"Ref": "EFSFileSystem"},
				"SubnetId": { "Ref": "Subnet" },
				"SecurityGroups": [{"Ref": "EFSSecurityGroup"}]        
			}
		},
		"EFSSecurityGroup": {
			"Type": "AWS::EC2::SecurityGroup",
			"Properties": {
				"GroupDescription": "Allowing access to EFS",
				"VpcId": {"Ref": "VPC"},
				"SecurityGroupIngress": [{
					"IpProtocol": "tcp",
					"FromPort": 2049,
					"ToPort": 2049,
					"SourceSecurityGroupId": {"Ref": "EC2SecurityGroup"}
				}]
			}
		}				
	}
}
```