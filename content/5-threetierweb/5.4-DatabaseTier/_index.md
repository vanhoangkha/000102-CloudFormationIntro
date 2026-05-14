---
title: "Checking Database Tier Access"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 5.4 </b> "
---

#### Checking Database Tier Access

1. Check and save the Database Endpoint.

![AWS CloudFormation](/images/4/00022.png?featherlight=false&width=90pc)

2. Connect to the Web tier EC2:

```
ssh -i <path_to_key_pair> ec2-user@<web_tier_ec2_private_ip>
```

* Then access the Database:

```
mysql --host=<database_endpoint_address> --user=<admin_name> --password=<password>
```

![AWS CloudFormation](/images/4/00023.png?featherlight=false&width=90pc)

3. Go back to the SSH session into Bastion Host and run the command:

```
nping -p 3306 <database_endpoint_address>
```
![AWS CloudFormation](/images/4/00024.png?featherlight=false&width=90pc)

4. Check the database

![AWS CloudFormation](/images/4/00025.png?featherlight=false&width=90pc)

5. Check the networking of the database.

![AWS CloudFormation](/images/5/0001.png?featherlight=false&width=90pc)

6. Check the Mutil-AZ of the Database.

![AWS CloudFormation](/images/5/0002.png?featherlight=false&width=90pc)