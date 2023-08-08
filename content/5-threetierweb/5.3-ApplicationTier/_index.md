---
title : "Check Access to the Application Tier"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

#### Check Access to the Application Tier


1. Check access to the Application Tier by running the following command:

```
curl <AppTierLoadBalancerURL> 
```


![AWS CloudFormation](/images/4/00018.png?featherlight=false&width=90pc)


2. TRun curl against the private IP address of the EC2 instance in the Application tier from the Web tier. You should see a Connection refused error.

```
curl -m 10 <app_tier_ec2_private_ip>
```

![AWS CloudFormation](/images/4/00019.png?featherlight=false&width=90pc)

3. Try to check a TCP ping using `nping` to see if you can receive a response on port TCP 80 or 22.

```
nping -p 22 <app_tier_ec2_private_ip>
```

![AWS CloudFormation](/images/4/00020.png?featherlight=false&width=90pc)

4. Port 80:

```
nping -p 80 <app_tier_ec2_private_ip>
```


![AWS CloudFormation](/images/4/00021.png?featherlight=false&width=90pc)