---
title: 'aws cloudformation security group'
author: ulysses

date: 2021-12-29
slug: aws-cloudformation-security-group
draft: false
---

AWS CloudFormation to create security groups. Includes self-refencing ingress and egress rules.

```
AWSTemplateFormatVersion: '2010-09-09'
Description: my-security-groups
######################################
Parameters:
  EC2Vpc:
    ConstraintDescription: Must be a valid VpcId
    Description: Select the VPC to use
    Type: AWS::EC2::VPC::Id
##############################################################################
Metadata:
  AWS::CloudFormation::Interface:
    ParameterGroups:
    - Label:
        default: VPC
      Parameters:
      - EC2Vpc
##############################################################################
Resources:
  EC2InstanceSecurityGroup1:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: 
        Ref: EC2Vpc
      GroupDescription: my-security-group-1
      GroupName: my-security-group-1
      SecurityGroupIngress:
        - {CidrIp: 10.0.0.0/8,                        IpProtocol: tcp,  FromPort: '80',      ToPort: '80',    Description: 'HTTP'}  
      SecurityGroupEgress:
        - {CidrIp: 10.0.0.0/8,                        IpProtocol: udp,  FromPort: '123',     ToPort: '123',   Description: 'NTP'}  
        - {CidrIp: 10.0.0.0/8,                        IpProtocol: tcp,  FromPort: '53',      ToPort: '53',    Description: 'DNS'}
      Tags:
        - {Key: Name,         Value: 'my-security-group-1'}
  EC2InstanceSecurityGroup2:
    Type: AWS::EC2::SecurityGroup
    Properties:
      VpcId: 
        Ref: EC2Vpc
      GroupDescription: my-security-group-2
      GroupName: my-security-group-2
      SecurityGroupIngress:
        - {CidrIp: 0.0.0.0/0,                        IpProtocol: tcp,  FromPort: '443',     ToPort: '443',   Description: 'HTTP'}  
        - {CidrIp: 0.0.0.0/0,                        IpProtocol: icmp, FromPort: '-1',      ToPort: '-1',    Description: 'ICMP ping'}
      SecurityGroupEgress:
        - {CidrIp: 10.0.0.0/8,                       IpProtocol: udp,  FromPort: '123',     ToPort: '123',   Description: 'NTP'}  
        - {CidrIp: 10.0.0.0/8,                       IpProtocol: tcp,  FromPort: '53',      ToPort: '53',    Description: 'DNS'}
        - {CidrIp: 0.0.0.0/0,                        IpProtocol: icmp, FromPort: '-1',      ToPort: '-1',    Description: 'ICMP ping'}
      Tags:
        - {Key: Name,         Value: 'my-security-group-2'}
  MyIngressSelfAll:
    Type: AWS::EC2::SecurityGroupIngress
    Properties:
      GroupId: !Ref EC2InstanceSecurityGroup2
      SourceSecurityGroupId: !GetAtt EC2InstanceSecurityGroup2.GroupId
      IpProtocol: -1
      FromPort: 0
      ToPort: 65535
  MyEgressSelfAll:
    Type: AWS::EC2::SecurityGroupEgress
    Properties: 
      GroupId: !Ref EC2InstanceSecurityGroup2
      DestinationSecurityGroupId: !GetAtt EC2InstanceSecurityGroup2.GroupId
      IpProtocol: -1 
      FromPort: 0
      ToPort: 65535
##############################################################################
Outputs:
  SecurityGroupId:
    Description: The Security Group that was created
    Value: {Ref: EC2InstanceSecurityGroup1}
    Value: {Ref: EC2InstanceSecurityGroup2}
  StackName:
    Description: Name of this stack for Fn::ImportValue use by children of top level stack
    Value: {Ref: 'AWS::StackName'}
```