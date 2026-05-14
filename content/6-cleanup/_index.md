---
title: "Cleaning up resources"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

#### Cleaning up resources

#### Deleting the CloudFormation Lambda stack

```
aws cloudformation delete-stack \
 --stack-name cfn-lambda-demo
```

#### Deleting the CloudFormation VPC stack

```
 aws cloudformation delete-stack \
  --stack-name cfn-vpc-demo 
```

![AWS CloudFormation](/images/3/0008.png?featherlight=false&width=90pc)