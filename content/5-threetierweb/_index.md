---
title : "Three-Tier Architecture"
date: 2024-01-01
weight : 5
chapter : false
pre : " <b> 5. </b> "
---
This is an AWS CloudFormation template, which is used to deploy a 3-tier architecture in the us-east-1 region. AWS CloudFormation is an infrastructure-as-code service that allows you to define and provision AWS resources using a template.

Here's a breakdown of the template:

- **Parameters**: These are input parameters that allow you to customize the deployment by providing values at runtime. The user is prompted to enter values for these parameters when launching the CloudFormation stack.

- **EnvironmentName**: An environment name that is prefixed to resource names. The default value is 3-Tier.
- **KeyPair**: The name of the SSH Key Pair for remote access to EC2 instances. This is used for securely connecting to instances using SSH.
- **DatabaseName**: The name of the MySQL database to be created. The default value is demo-database.
- **MasterUsername**: The master username for the RDS (Relational Database Service) database.
- **MasterUserPassword**: The master password for the RDS database.
- **MySQLDBSubnetGroupName**: The name for the RDS Database Instance Subnet Group. This is a group of subnets where the RDS instance will be deployed.
- **VpcCIDR**: The IP range (CIDR notation) for the Virtual Private Cloud (VPC) to be created. The default value is 10.100.0.0/16.
- **PublicSubnet1CIDR, PublicSubnet2CIDR, PublicSubnet3CIDR**: The IP ranges for the public subnets in different Availability Zones (AZs).
- **PrivateSubnet1CIDR, PrivateSubnet2CIDR, PrivateSubnet3CIDR, PrivateSubnet4CIDR**: The IP ranges for the private subnets in different Availability Zones.
- **Resources**: These are the AWS resources that will be created as part of the CloudFormation stack. The template defines various AWS resources, including VPC, subnets, security groups, NAT gateway, Elastic Load Balancers, EC2 instances, RDS instance, etc., to build a 3-tier architecture.

- The VPC, Internet Gateway, NAT Gateway, and subnet resources are used to set up the network infrastructure.
- The security groups define the inbound and outbound rules for communication between different tiers of the architecture.
- The EC2 instances are launched with specific configurations, including user data scripts for customizing the instances.
- The Application Load Balancers (ALBs) distribute incoming traffic to the EC2 instances in the Web and App tiers.
- The RDS instance (MySQLDatabase) provides the database layer for the architecture.
- **Outputs**: These are the values that will be displayed after the stack is successfully created. The values include information like the public IP address of the Bastion Host (used for SSH access), URLs of the Web and App Tier Load Balancers, and the endpoint address and port for the MySQL Database.

In summary, this CloudFormation template deploys a 3-tier architecture consisting of a Bastion Host (for secure SSH access), a Web Tier (with an Application Load Balancer), an App Tier (also with an Application Load Balancer), and a MySQL Database (RDS) in the specified AWS region. The architecture is set up with public and private subnets, security groups, and other networking configurations to ensure proper communication and security between the tiers.

