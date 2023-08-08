---
title : "Kiểm tra truy cập Application Tier"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 5.3 </b> "
---

#### Kiểm tra truy cập Application Tier


1. Kiểm tra truy cập vào Application Tier qua lệnh sau:

```
curl <AppTierLoadBalancerURL> 
```


![AWS CloudFormation](/images/4/00018.png?featherlight=false&width=90pc)


2. Thực hiện  curl địa chỉ Private IP của EC2 ở Application tier từ Web tier. Chúng ta sẽ thấy kết quả không thể.

```
curl -m 10 <app_tier_ec2_private_ip>
```

![AWS CloudFormation](/images/4/00019.png?featherlight=false&width=90pc)

3. Thử kiểm tra một TCP ping qua nping để xem chúng ta có thể nhận được phản hồi trên cổng TCP 80 hoặc 22 không?

```
nping -p 22 <app_tier_ec2_private_ip>
```

![AWS CloudFormation](/images/4/00020.png?featherlight=false&width=90pc)

4. Port 80:

```
nping -p 80 <app_tier_ec2_private_ip>
```


![AWS CloudFormation](/images/4/00021.png?featherlight=false&width=90pc)