---
title: "Preparation Steps"
date: 2024-01-01
weight: 2
chapter: false
pre: "<b>2. </b>"
---

#### Preparation Steps

1. To perform this workshop, we need to set up the environment on Cloud9. Access **Cloud9** and select **Create environment**.

![AWS CloudFormation](/images/1/0001.png?featherlight=false&width=90pc)

2. Set the **Name** for this environment. For example, we can name it **CloudFormation-Env**.

![AWS CloudFormation](/images/1/0002.png?featherlight=false&width=90pc)

3. Next, choose the **Instance type** that suits your environment. For instance, select **t3.small**.

![AWS CloudFormation](/images/1/0003.png?featherlight=false&width=90pc)

4. Leave all other values as default and then click **Create**.

![AWS CloudFormation](/images/1/0004.png?featherlight=false&width=90pc)

5. After about 3 minutes, the environment will be ready, and we can click **Open**.

![AWS CloudFormation](/images/1/0005.png?featherlight=false&width=90pc)

6. Access **IAM**, select **Role**, and then choose **Create role**. Click **Next**.

![AWS CloudFormation](/images/1/0006.png?featherlight=false&width=90pc)

7. Find and select **AdministratorAccess** as the **Permission policy**.

![AWS CloudFormation](/images/1/0007.png?featherlight=false&width=90pc)

8. Next, click **Next**.

![AWS CloudFormation](/images/1/0008.png?featherlight=false&width=90pc)

9. Set a name for the Role. For example: **IaC-Role**.

![AWS CloudFormation](/images/1/0009.png?featherlight=false&width=90pc)

10. Double-check everything and click **Create role**.

![AWS CloudFormation](/images/1/00010.png?featherlight=false&width=90pc)

11. Go back to the **Cloud9** interface, and select **Manage EC2 instance**.

![AWS CloudFormation](/images/1/00011.png?featherlight=false&width=90pc)

12. You will be redirected to the EC2 page. Choose **Actions**:

    - Select **Security**
    - Choose **Modify IAM role**

![AWS CloudFormation](/images/1/00012.png?featherlight=false&width=90pc)

13. Select the Role you just created and click **Update IAM role**.

![AWS CloudFormation](/images/1/00013.png?featherlight=false&width=90pc)

14. You need to clone the resources from the repository:

```bash
git clone https://github.com/AWS-First-Cloud-Journey/CloudFormation-series.git 
```

![AWS CloudFormation](/images/1/00014.png?featherlight=false&width=90pc)