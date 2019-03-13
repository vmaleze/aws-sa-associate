# Automation

## CloudFormation

* Infrastructure as a code
* Works with deltas when redeploying the same CloudFormation
* Made of stacks
* You can have multi stacks templates and reference them through s3

## Systems Manager

* Suite of tools for EC2 automation
* You need an AWS System Manager Agent on the machine
* Allows to connect through SSH without access keys (Session Manager)
* Allows to run commands on multiple servers at once (Run command)
* Automation to execute actions in a more global way (Automation)
* Patch Manager
* State manager
* Maintenance Window

## Elastic Beanstalk

* PaaS
* Use to build webapp without knowledge on AWS
* Manages the application stack for you
  * Completely transparent
  * Automatically scale up and down
* Configured once

## OpsWorks

* Configuration management services
* Interface for chef and puppets
* Complex because you need to specify every layer you need