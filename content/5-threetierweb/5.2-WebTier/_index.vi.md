---
title : "Kiểm tra truy cập Web Tier"
date: 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.2 </b> "
---

#### Kiểm tra truy cập Web Tier


1. Sau khi tạo thành công, chúng ta chọn **Output**. Sao chép giá trị **WebTierLoadBalancerURL** vào trình duyệt.

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)

2. Trên trình duyệt, chúng ta sẽ thấy dòng chữ **This Amazon EC2 instance is located in Availability Zone: us-east-1a**

![AWS CloudFormation](/images/4/00011.png?featherlight=false&width=90pc)

3. Sau đó bạn có thể tải lại trang sẽ đổi AZ khác: **This Amazon EC2 instance is located in Availability Zone: us-east-1b**

![AWS CloudFormation](/images/4/00012.png?featherlight=false&width=90pc)


4. Quay lại phần **Output** sao chép giá trị của **BastionHostIP**

![AWS CloudFormation](/images/4/00017.png?featherlight=false&width=90pc)

5. Thực hiện SSH vào Bastion Host dựa vào keypair và IP vừa sao chép.

![AWS CloudFormation](/images/4/00013.png?featherlight=false&width=90pc)

6. SSH thành công.

![AWS CloudFormation](/images/4/00014.png?featherlight=false&width=90pc)

7. Tạo file **cfn-keypair.pem** và sao chép nội dung key từ máy tính cá nhân, sau đó lưu lại bằng lệnh **:wq!** 

![AWS CloudFormation](/images/4/00015.png?featherlight=false&width=90pc)

8. Thực hiện trung gian ssh vào Web tier EC2 instance qua các lệnh sao:

```
chmod 400 <path_key_pair> 
ssh -i <path_to_key_pair> ec2-user@<web_tier_ec2_private_ip>
```

![AWS CloudFormation](/images/4/00016.png?featherlight=false&width=90pc)