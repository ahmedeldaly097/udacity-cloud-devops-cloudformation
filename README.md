# Deploy a high-availability web app using CloudFormation
This is one of the project in Udacity Advanced Cloud DevOps Engineer Nanodegree.

## Project Overview
Assume that one company is creating Instagram like application. Developers have developed the code and pushed the code into the S3 bucket on AWS. Now the task is to create the infrastructure for deploying that application in an automated way using CloudFormation following the best practices and once infrastructure is ready, deploy that application code onto that infrastructures.

## Project Files
- `/screenshots` : screenshots for the project.
- `create.sh` : Creating file.
- `update.sh` : Updating file.
- `delete.sh` : Deleting file.
- `diagram.png` : This describes the architecture diagram of this project.
- `network-parameter.json` : Parameters file for network cloud formation stack.
- `network.yml` : CloudFormation template for creating networking resources for this project.
- `servers-parameter.json` : Parameters file for servers cloud formation stack.
- `servers.yml` : CloudFormation template for creating servers for this project.

## Project Setup

- Create networking resources using cloud formation template.
```
$ ./create.sh infra-network network.yml network-parameter.json
```
-   Following resources are created after executing above command:
    -   VPC
    -   Subnets
    -   Route Tables
    -   Routes
    -   Internet Gateway
    -   NAT Gateways
- Create servers for Udagram App which pulls source code from S3 bucket automatically while starting.
```
$ ./create.sh infra-servers servers.yml servers-parameter.json
```
-   Following resources are created after executing above command:
    -   Security Groups
    -   IAM Role, Policy, Instance Profile
    -   Launch configuration
    -   Auto Scaling Group
    -   Load Balancer
    -   Target Group
- Once the above steps are complete, you can find the URL of application in the outputs section of `infra-servers` CloudFormarion stack.
