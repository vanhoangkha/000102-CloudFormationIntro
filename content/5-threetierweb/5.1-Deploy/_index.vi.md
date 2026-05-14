---
title : "Triển khai CloudFormation Stack"
date: 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1 </b> "
---

#### Triển khai CloudFormation Stack


1. Truy cập vào **EC2** và chọn **Keypair**, sau đó chọn **Create key pair**.

![AWS CloudFormation](/images/4/0001.png?featherlight=false&width=90pc)

2. Thực hiện tạo keypair. Đặt tên cho keypair chúng ta sẽ dùng để tạo CloudFormation stack.

![AWS CloudFormation](/images/4/0002.png?featherlight=false&width=90pc)

3. Tạo keypair thành công.

![AWS CloudFormation](/images/4/0003.png?featherlight=false&width=90pc)

4. Chúng ta truy cập vào **CloudFormation**

- Chọn **Create stack**.
- Chọn **With new resources (standard)**


![AWS CloudFormation](/images/4/0004.png?featherlight=false&width=90pc)

5. Thực hiện tạo stack

- Chọn **Template is ready**
- Chọn **Upload a template file**
- Tải file template về tại [đây](https://github.com/AWS-First-Cloud-Journey/CloudFormation-series/blob/master/day-3/cfn-aws-three-tier-demo.yaml)
- Chọn **Choose file** và chọn file vừa tải về.

![AWS CloudFormation](/images/4/0005.png?featherlight=false&width=90pc)

5. Đặt tên cho **Stack name**. Ví dụ: **cfn-aws-three-tier-demo**

![AWS CloudFormation](/images/4/0006.png?featherlight=false&width=90pc)

6. Thực hiện hoàn thành các thông tin trong phần **Parameters**

![AWS CloudFormation](/images/4/0007.png?featherlight=false&width=90pc)

7. Sau khi hoàn thành thông tin, chọn **Next**

![AWS CloudFormation](/images/4/0008.png?featherlight=false&width=90pc)

8. Chọn **Next**

![AWS CloudFormation](/images/4/0009.png?featherlight=false&width=90pc)

9. Kiểm tra lại và chọn **Submit**

![AWS CloudFormation](/images/4/00010.png?featherlight=false&width=90pc)

10. Sau khi tạo thành công, chúng ta chọn **Output**. Sao chép giá trị **WebTierLoadBalancerURL** vào trình duyệt.

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)
