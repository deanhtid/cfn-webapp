# cfn-webapp
Simple Scalable Web App using Apache and ECS

## Overview
A modern automated, highly available web application written in CloudFormation utilising the following AWS services:

- ECS
- EC2
- CloudWatch
- Application Load Balancer
- AutoScaling Groups
- NAT Gateways
- Internet Gateway

The architecture consists of: 

- Two Private Subnets where the app is hosted
- Two Public Subnets hosting the Application Load Balancer
- Users will access the application through a public DNS endpoint (provided by cloudformation)

As part of the deployment i've utilised busybox which is a docker container that has a bunch of utilities allowing me to to script and apply the html, css etc

## Requirements 
- AWS Account
- Cloudformation

## Installing
- First, create the stack using the vpc.yml file
  - update the parameter for the Class B CIDR range 1-255
  - run the template
- Secondly run the app.yaml file
  - update the ParentVPCStack parameter to the name of the vpc template stack created previously
  - update the other parameters or leave the defaults
  - run the template
- The app url will be provided in the stack outputs
- Test the app is working by following the url in your favourite browser

### Todo
- Review IAM policies and lock down to least privilege
- Use HTTPS
 - create a certificate using ACM and assign to the listener
 - update ports to 443
- enable logging on the alb
  - create an s3 bucket for the logs
  - create and assign a kms key to encrypt log data
- Further lock down the security groups and ACL's
- Explicitly define outbound traffic in the SG's
- I can fully automate the deployment process but I prefer to split out each section hence the two files
- Add an Web Application Firewall to the ALB





