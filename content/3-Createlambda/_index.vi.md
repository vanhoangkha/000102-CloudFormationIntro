---
title : "Tạo Lambda function"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

#### Tạo Lambda function

#### Giải thích CloudFormation template:

- **AWSTemplateFormatVersion**: Đây chỉ định phiên bản của định dạng file template AWS CloudFormation được sử dụng (2010-09-09 trong trường hợp này).

- **Description**: Đây là mô tả ngắn gọn về file template.

- **Resources**: Phần này xác định các nguồn tài nguyên cần tạo trong CF.

- **LambdaRole**: Đây là tài nguyên AWS::IAM::Role để xác định role cho hàm Lambda. Nó định nghĩa một role có tên "lambda-role" và xác định policy cho role đó.

- **LambdaFunctionDemo**: Đây là tài nguyên AWS::Lambda::Function để tạo hàm Lambda. Nó đặt tên hàm là "CfnLambdaDemo" và xác định các thuộc tính khác như handler, mã nguồn, runtime, kích thước bộ nhớ, thời gian chờ, và role.

- **Outputs**: Phần này xác định các giá trị đầu ra của CloudFormation template.

- **LambdaRoleArn**: Đây là một giá trị đầu ra để cung cấp ARN (Amazon Resource Name) của role LambdaRole.

- **LambdaFunctionName**: Đây là một giá trị đầu ra để cung cấp tên của hàm Lambda (LambdaFunctionDemo).

- File template này tạo ra một role IAM và một hàm Lambda, và cung cấp các giá trị đầu ra để sử dụng trong các quy trình tiếp theo hoặc trong cấu hình hệ thống.

1. Sau khi clone về chúng ta sẽ đến đúng đường dẫn các template CloudFormation.

```
cd CloudFormation-series
cd day-1
```

![AWS CloudFormation](/images/1/00015.png?featherlight=false&width=90pc)

2. Bạn xem qua file yaml là template để tạo Lambda Function.

![AWS CloudFormation](/images/1/00016.png?featherlight=false&width=90pc)

3. Thực hiện tạo Lambda Function bằng lệnh sau:

```
aws cloudformation create-stack \
 --stack-name cfn-lambda-demo \
 --template-body file://lambda.yaml \
 --capabilities CAPABILITY_NAMED_IAM
```

![AWS CloudFormation](/images/1/00017.png?featherlight=false&width=90pc)

4. Sau khoảng 5 phút. CloudFormation stack tạo thành công.

![AWS CloudFormation](/images/2/0001.png?featherlight=false&width=90pc)

5. Truy cập vào giao diện **CloudFormation**, kiểm tra CloudFormation stack và xem các **Event**.

![AWS CloudFormation](/images/2/0002.png?featherlight=false&width=90pc)

6. Kiểm tra phần **Resources** đã tạo ra là LambdaFunctionDemo và LambdaRole.

![AWS CloudFormation](/images/2/0003.png?featherlight=false&width=90pc)

7. Kiểm tra phần **Output**

![AWS CloudFormation](/images/2/0004.png?featherlight=false&width=90pc)

8. Truy cập vào **Lambda**, chúng ta sẽ thấy LambdaFunction đã được tạo.

![AWS CloudFormation](/images/2/0005.png?featherlight=false&width=90pc)

9. Truy cập vào Lambda Function, chọn **Test** và thực hiện **Test event**.

![AWS CloudFormation](/images/2/0006.png?featherlight=false&width=90pc)

10. Thực hiện tạo **Create new event** và **Event name**

![AWS CloudFormation](/images/2/0007.png?featherlight=false&width=90pc)

11. Sau khi test bạn sẽ thấy **Log output**

![AWS CloudFormation](/images/2/0008.png?featherlight=false&width=90pc)