---
title: "Create VPC and EC2"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

#### Create VPC and EC2


The AWS CloudFormation template you provided will create an EC2 instance within a VPC and allow you to access it via SSM. The template defines the following resources:

- A VPC
- A subnet
- An internet gateway
- A route table
- A route
- A subnet route table association
- A security group
- An IAM role
- An IAM instance profile
- An EC2 instance

The template uses the following mappings:

- AWSInstanceType2Arch: This mapping maps an EC2 instance type to its architecture.
- AWSRegionArch2AMI: This mapping maps an AWS region and architecture to an AMI ID.

The template also uses the following CloudFormation intrinsic functions:

- Fn::FindInMap: This function returns the value of a mapping at a specific key.

To deploy the template, you can use the following command:

```
aws cloudformation deploy --template-file CloudFormationTemplate.yaml --stack-name MyStack
```



Once the template has been deployed, you can access the EC2 instance via SSM by using the following command:

```
aws ssm start-session --target <instance-id>
```

This command will start a session with the EC2 instance and allow you to execute commands on the instance.


#### Explanation of CloudFormation Template

This template creates an EC2 instance within a VPC and allows access to the instance through AWS Systems Manager (SSM). Below is a detailed description of the sections in the template:

- **AWSTemplateFormatVersion**: The version of the template format.
- **Description**: A brief description of the template.
- **Parameters**: Defines parameters that can be used to customize the deployment process.
- **InstanceType**: A parameter to specify the EC2 instance type. The default is "t2.small", and it only allows values "t2.small" or "t2.medium".
- **Mappings**: Defines mappings between values. In this case, mappings are used to associate EC2 instance types with their corresponding image IDs.
- **Resources**: Defines the resources that the template creates.
- **VPC**: Creates a Virtual Private Cloud (VPC).
- **Subnet**: Creates a subnet within the VPC.
- **InternetGateway**: Creates an Internet Gateway to connect the VPC to the Internet.
- **AttachGateway**: Attaches the Internet Gateway to the VPC.
- **RouteTable**: Creates a Route Table for the VPC.
- **Route**: Adds a route in the Route Table to allow traffic to the Internet through the Internet Gateway.
- **SubnetRouteTableAssociation**: Associates the subnet with the Route Table.
- **InstanceSecurityGroup**: Creates a Security Group to manage data flows and security rules for the EC2 instance.
- **RoleForEC2**: Creates an IAM role to be assigned to the EC2 instance, allowing it to access AWS services.
- **InstanceProfile**: Creates an Instance Profile to be associated with the EC2 instance, enabling it to use the created IAM role.
- **WebServeerInstance**: Creates an EC2 instance using the specified parameters and associates it with the VPC, Subnet, Security Group, and IAM role created.

This template creates a simple environment for deploying an EC2 instance within a VPC and allowing access through AWS Systems Manager (SSM).

#### Creating AWS CloudFormation Resources

1. In the previous section, we used AWS CloudFormation to create a Lambda function. In this section, we will create networking infrastructure (VPC and VPC components) along with an EC2 instance and an SSM role.

![AWS CloudFormation](/images/3/0001.png?featherlight=false&width=90pc)

1. Navigate to the directory containing the template and use the following command to deploy the stack:


```
aws cloudformation create-stack \
 --stack-name cfn-vpc-demo \
 --template-body file://vpc.yaml \
 --parameters ParameterKey=InstanceType,ParameterValue=t2.medium \
 --capabilities CAPABILITY_NAMED_IAM
```

![AWS CloudFormation](/images/3/0002.png?featherlight=false&width=90pc)

3. After 5 minutes, you can check the CloudFormation console and the event log to see that the resources have been created.

![AWS CloudFormation](/images/3/0003.png?featherlight=false&width=90pc)

4. Check the Resources section to see that the resources have been created.

![AWS CloudFormation](/images/3/0004.png?featherlight=false&width=90pc)

5. Check the EC2 console to see that a new instance has been created.

- Click **CConnect**.

![AWS CloudFormation](/images/3/0005.png?featherlight=false&width=90pc)

6. In the **Connect** to instance dialog, select **Session Manager** and click **Connect**.

![AWS CloudFormation](/images/3/0006.png?featherlight=false&width=90pc)

7. A new session is opened and you can try pinging a website using the following command:

```
ping amazon.com -c5
```

![AWS CloudFormation](/images/3/0007.png?featherlight=false&width=90pc)


#### Conclusion
In this section, we learned how to use AWS CloudFormation to create networking infrastructure (VPC and VPC components) along with an EC2 instance and an SSM role.