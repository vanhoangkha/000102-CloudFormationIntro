---
title: "Deploying CloudFormation Stack"
date: 2024-01-01
weight: 1
chapter: false
pre: "<b>5.1.  </b>"
---

### Deploying CloudFormation Stack

1. Access **EC2** and select **Keypair**, then choose **Create key pair**.

![AWS CloudFormation](/images/4/0001.png?featherlight=false&width=90pc)

2. Proceed with creating the keypair. Name the keypair that will be used to create the CloudFormation stack.

![AWS CloudFormation](/images/4/0002.png?featherlight=false&width=90pc)

3. Keypair created successfully.

![AWS CloudFormation](/images/4/0003.png?featherlight=false&width=90pc)

4. Access **CloudFormation**

- Select **Create stack**.
- Choose **With new resources (standard)**

![AWS CloudFormation](/images/4/0004.png?featherlight=false&width=90pc)

5. Proceed with creating the stack

- Select **Template is ready**
- Choose **Upload a template file**
- Download the template file [here](https://github.com/AWS-First-Cloud-Journey/CloudFormation-series/blob/master/day-3/cfn-aws-three-tier-demo.yaml)
- Select **Choose file** and choose the downloaded file.

![AWS CloudFormation](/images/4/0005.png?featherlight=false&width=90pc)

6. Set the **Stack name**. For example: **cfn-aws-three-tier-demo**

![AWS CloudFormation](/images/4/0006.png?featherlight=false&width=90pc)

7. Complete the information in the **Parameters** section.

![AWS CloudFormation](/images/4/0007.png?featherlight=false&width=90pc)

8. After completing the information, select **Next**

![AWS CloudFormation](/images/4/0008.png?featherlight=false&width=90pc)

9. Select **Next**

![AWS CloudFormation](/images/4/0009.png?featherlight=false&width=90pc)

10. Review and select **Submit**

![AWS CloudFormation](/images/4/00010.png?featherlight=false&width=90pc)

11. Once successfully created, select **Output**. Copy the value of **WebTierLoadBalancerURL** into the browser.

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)
