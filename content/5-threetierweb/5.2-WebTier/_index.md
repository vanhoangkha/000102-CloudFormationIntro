---
title: "Web Tier Access Test"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: "<b>5.2 </b>"
---

#### Web Tier Access Test

1. After successful creation, select **Output**. Copy the value of **WebTierLoadBalancerURL** and paste it into your web browser.

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)

2. In the web browser, you will see the text line **This Amazon EC2 instance is located in Availability Zone: us-east-1a**.

![AWS CloudFormation](/images/4/00011.png?featherlight=false&width=90pc)

3. You can then refresh the page to switch to another AZ: **This Amazon EC2 instance is located in Availability Zone: us-east-1b**.

![AWS CloudFormation](/images/4/00012.png?featherlight=false&width=90pc)

4. Go back to the **Output** section and copy the value of **BastionHostIP**.

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)

5. SSH into the Bastion Host using the keypair and IP you just copied.

![AWS CloudFormation](/images/4/00013.png?featherlight=false&width=90pc)

6. SSH connection successful.

![AWS CloudFormation](/images/4/00014.png?featherlight=false&width=90pc)

7. Create the **cfn-keypair.pem** file and copy the key content from your local computer, then save and exit using the command **:wq!**.

![AWS CloudFormation](/images/4/00015.png?featherlight=false&width=90pc)

8. Perform an intermediate SSH connection to the Web tier EC2 instance using the following commands:

```bash
chmod 400 <path_key_pair>
ssh -i <path_to_key_pair> ec2-user@<web_tier_ec2_private_ip>
```


![AWS CloudFormation](/images/4/00016.png?featherlight=false&width=90pc)