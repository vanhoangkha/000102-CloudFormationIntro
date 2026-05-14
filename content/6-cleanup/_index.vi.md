---
title : "Dọn dẹp tài nguyên"
date: 2024-01-01
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Dọn dẹp tài nguyên

#### Xóa CloudFormation Lambda stack

```
aws cloudformation delete-stack \
 --stack-name cfn-lambda-demo
```

#### Xóa CloudFormation VPC stack


```
 aws cloudformation delete-stack \
  --stack-name cfn-vpc-demo 
```

![AWS CloudFormation](/images/3/0008.png?featherlight=false&width=90pc)