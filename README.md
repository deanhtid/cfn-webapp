# cfn-webapp
Simple Scalable Web App using Apache and ECS

## Overview
A modern automated, highly available web application written in CloudFormation utilising the following AWS services:

- ECS
- EC2
- CloudWatch
- Application Load Balancer
- AutoScaling Groups

The architecture consists of: 

- Two Private Subnets where the app is hosted
- Two Public Subnets hosting the Application Load Balancer
- Users will access the application through a public DNS endpoint (provided by cloudformation)

## Requirements 
- AWS Account
- Cloudformation

## Installing
- First, create stack using the vpc.yml file
  - update the parameter for the Class B CIDR range 1-255
  - run the template
- Secondly run the app.yaml file
  - update the ParentVPCStack parameter to the name of the vpc template stack created previously
  - update the other parameters or leave the defaults
  - run the template
- The app url will be provided in the stack outputs
- Test the app is working by following the url in your favourite browser


