---
title : "Tạo VPC và EC2"
date: 2024-01-01
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

#### Tạo VPC và EC2

#### Giải thích CloudFormation template
Template này tạo ra một EC2 instance trong một VPC và cho phép truy cập vào instance thông qua AWS Systems Manager (SSM). Dưới đây là mô tả chi tiết của các phần trong template:

- **AWSTemplateFormatVersion**: Phiên bản của template format.
- **Description**: Mô tả ngắn về template.
- **Parameters**: Định nghĩa các tham số (parameters) có thể được sử dụng để tùy chỉnh quá trình triển khai.
- **InstanceType**: Tham số để chỉ định loại EC2 instance. Mặc định là "t2.small", và chỉ cho phép giá trị "t2.small" hoặc "t2.medium".
- **Mappings**: Định nghĩa các ánh xạ (mappings) giữa các giá trị. Trong trường hợp này, ánh xạ được sử dụng để ánh xạ giữa loại instance EC2 và image ID tương ứng.
- **Resources**: Định nghĩa các nguồn (resources) mà template tạo ra.
- **VPC**: Tạo một VPC (Virtual Private Cloud).
- **Subnet**: Tạo một subnet trong VPC.
- **InternetGateway**: Tạo một Internet Gateway để kết nối VPC với Internet.
- **AttachGateway**: Gắn Internet Gateway với VPC.
- **RouteTable**: Tạo một Route Table cho VPC.
- **Route**: Thêm một route trong Route Table để cho phép traffic ra Internet thông qua Internet Gateway.
- **SubnetRouteTableAssociation**: Liên kết subnet với Route Table.
- **InstanceSecurityGroup**: Tạo một Security Group để quản lý các luồng dữ liệu và quy tắc bảo mật cho instance EC2.
- **RoleForEC2**: Tạo một IAM role để gán cho instance EC2, cho phép nó truy cập vào các dịch vụ AWS.
- **InstanceProfile**: Tạo một Instance Profile để kết hợp với instance EC2, cho phép nó sử dụng IAM role đã tạo.
- **WebServeerInstance**: Tạo một EC2 instance sử dụng các thông số đã chỉ định và liên kết với VPC, Subnet, Security Group, và IAM role đã tạo.
- Template này tạo ra một môi trường đơn giản để triển khai một EC2 instance trong một VPC và cho phép truy cập vào instance thông qua SSM. Bằng cách triển khai template này, bạn có thể tự động tạo và cấu hình một môi trường EC2 một cách nhất quán.

1. Sau phần đầu chúng ta sử dụng CloudFormation tạo Lambda function thì phần tiếp theo chúng ta sẽ tạo hạ tầng về networking (VPC và các thành phần của VPC) cùng với EC2 và role dành cho SSM. Quan sát template tạo tài nguyên.

![AWS CloudFormation](/images/3/0001.png?featherlight=false&width=90pc)

2. Di chuyển đến thư mục chứa template và dùng lệnh sau để triển khai stack:


```
aws cloudformation create-stack \
 --stack-name cfn-vpc-demo \
 --template-body file://vpc.yaml \
 --parameters ParameterKey=InstanceType,ParameterValue=t2.medium \
 --capabilities CAPABILITY_NAMED_IAM
```

![AWS CloudFormation](/images/3/0002.png?featherlight=false&width=90pc)

3. Sau 5 phút, bạn có thể kiểm tra giao diện CloudFormation và Event tạo tài nguyên.

![AWS CloudFormation](/images/3/0003.png?featherlight=false&width=90pc)

4. Kiểm tra phần  **Resources** đã tạo.

![AWS CloudFormation](/images/3/0004.png?featherlight=false&width=90pc)

5. Bạn kiểm tra giao diện  **EC2** sẽ có 1 instance mới tạo.

- Chọn **Connect**

![AWS CloudFormation](/images/3/0005.png?featherlight=false&width=90pc)

6. Trong giao diện **Connect to instance**, chọn **Session Manager** và chọn **Connect**.

![AWS CloudFormation](/images/3/0006.png?featherlight=false&width=90pc)

7. Session mới mở ra và bạn thử ping tới một trang bằng lệnh:

```
ping amazon.com -c5
```

![AWS CloudFormation](/images/3/0007.png?featherlight=false&width=90pc)


