---
title: "Creating Lambda Function"
date: 2024-01-01
weight: 3
chapter: false
pre: "<b>3. </b>"
---

#### Creating Lambda Function

#### Explanation of CloudFormation template:

- **AWSTemplateFormatVersion**: This specifies the version of the AWS CloudFormation template format used (2010-09-09 in this case).

- **Description**: This provides a brief description of the template file.

- **Resources**: This section defines the resources to be created in the CloudFormation stack.

- **LambdaRole**: This is an AWS::IAM::Role resource to define the role for the Lambda function. It defines a role named "lambda-role" and specifies the policy for that role.

- **LambdaFunctionDemo**: This is an AWS::Lambda::Function resource to create the Lambda function. It names the function "CfnLambdaDemo" and specifies other attributes such as handler, source code, runtime, memory size, timeout, and role.

- **Outputs**: This section defines the output values of the CloudFormation template.

- **LambdaRoleArn**: This is an output value to provide the ARN (Amazon Resource Name) of the LambdaRole.

- **LambdaFunctionName**: This is an output value to provide the name of the Lambda function (LambdaFunctionDemo).

- This template creates an IAM role and a Lambda function, and provides output values to use in subsequent processes or system configurations.

1. Clone the repository and navigate to the CloudFormation templates directory:

```
cd CloudFormation-series
cd day-1
```

![AWS CloudFormation](/images/1/00015.png?featherlight=false&width=90pc)

2. Take a look at the `lambda.yaml` file, which is the template for creating the Lambda Function.

![AWS CloudFormation](/images/1/00016.png?featherlight=false&width=90pc)

3. Create the Lambda Function using the following command:

```
aws cloudformation create-stack \
 --stack-name cfn-lambda-demo \
 --template-body file://lambda.yaml \
 --capabilities CAPABILITY_NAMED_IAM
```

![AWS CloudFormation](/images/1/00017.png?featherlight=false&width=90pc)

4. After about 5 minutes, the CloudFormation stack will be created successfully.

![AWS CloudFormation](/images/2/0001.png?featherlight=false&width=90pc)

5. Go to the **CloudFormation** console, check the CloudFormation stack, and view the **Events**.

![AWS CloudFormation](/images/2/0002.png?featherlight=false&width=90pc)

6. Check the **Resources** section, which should contain LambdaFunctionDemo and LambdaRole.
![AWS CloudFormation](/images/2/0003.png?featherlight=false&width=90pc)

7. Check the **Output** section.
![AWS CloudFormation](/images/2/0004.png?featherlight=false&width=90pc)

8. Go to **Lambda**, where you will see that LambdaFunction has been created.
![AWS CloudFormation](/images/2/0005.png?featherlight=false&width=90pc)

9. Go to the Lambda Function, select **Test**, and perform **Test event**.
![AWS CloudFormation](/images/2/0006.png?featherlight=false&width=90pc)

10. Create a **Create new event** and **Event name**.
![AWS CloudFormation](/images/2/0007.png?featherlight=false&width=90pc)

11. After testing, you will see the **Log output**.
![AWS CloudFormation](/images/2/0008.png?featherlight=false&width=90pc)