---
title : "Kiểm tra truy cập Database Tier"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 5.4 </b> "
---

#### Kiểm tra truy cập Database Tier


1. Kiểm tra và ghi chứ lại Database Endpoint. 

![AWS CloudFormation](/images/4/00022.png?featherlight=false&width=90pc)

2. Kết nối vào EC2 của Web tier:

```
ssh -i <path_to_key_pair> ec2-user@<web_tier_ec2_private_ip>
```

- Sau đó truy cập vào Database:

```
mysql --host=<database_endpoint_address> --user=<admin_name> --password=<password>
```

![AWS CloudFormation](/images/4/00023.png?featherlight=false&width=90pc)

3. Quay lại session SSH vào Bastion Host thực hiện lệnh:

```
nping -p 3306 <database_endpoint_address>
```

![AWS CloudFormation](/images/4/00024.png?featherlight=false&width=90pc)

4. Kiểm tra database 

![AWS CloudFormation](/images/4/00025.png?featherlight=false&width=90pc)

5. Kiểm tra phần networking của database.

![AWS CloudFormation](/images/5/0001.png?featherlight=false&width=90pc)

6. Kiểm tra Mutil-AZ của Database.

![AWS CloudFormation](/images/5/0002.png?featherlight=false&width=90pc)

