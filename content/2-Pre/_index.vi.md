---
title : " Các bước chuẩn bị"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b>2. </b> "
---

#### Các bước chuẩn bị

1. Để thực hiện bài workshop này chúng ta cần chuẩn bị môi trường trên Cloud9. Truy cập vào **Cloud9** và chọn **Create environment**

![AWS CloudFormation](/images/1/0001.png?featherlight=false&width=90pc)

2. Đặt tên cho **Name**. Ví dụ bài này là **CloudFormation-Env**

![AWS CloudFormation](/images/1/0002.png?featherlight=false&width=90pc)

3. Sau đó, bạn chọn **Instance type** mà bạn thấy phù hợp với môi trường bạn cần dùng. Ví dụ **t3.small**

![AWS CloudFormation](/images/1/0003.png?featherlight=false&width=90pc)

4. Tất cả giá trị còn lại để mặc định và sau đó chọn **Create**.

![AWS CloudFormation](/images/1/0004.png?featherlight=false&width=90pc)

5. Sau khoảng 3 phút, môi trường đã tạo xong và chúng ta chọn **Open**. 

![AWS CloudFormation](/images/1/0005.png?featherlight=false&width=90pc)

6. Truy cập vào **IAM**, chọn **Role** và **Create role**. Sau đó chọn **Next**.

![AWS CloudFormation](/images/1/0006.png?featherlight=false&width=90pc)

7. Tìm và chọn **Permission policy** là **AdministratorAccess**.

![AWS CloudFormation](/images/1/0007.png?featherlight=false&width=90pc)

8. Sau đó, chúng ta chọn **Next**.

![AWS CloudFormation](/images/1/0008.png?featherlight=false&width=90pc)

9. Đặt tên Role. Ví dụ: **IaC-Role**

![AWS CloudFormation](/images/1/0009.png?featherlight=false&width=90pc)

10. Kiểm tra lại một lần nữa và chọn **Create role**.

![AWS CloudFormation](/images/1/00010.png?featherlight=false&width=90pc)

11. Quay lại giao diện **Cloud9**, bạn chọn **Manage EC2 instance**.

![AWS CloudFormation](/images/1/00011.png?featherlight=false&width=90pc)

12. Bạn sẽ được chuyển hướng đến trang EC2 và chọn **Actions**

    - Chọn **Security**
    - Chọn **Modify IAM role**

![AWS CloudFormation](/images/1/00012.png?featherlight=false&width=90pc)

13. Chúng ta sẽ chọn Role vừa tạo và chọn **Update IAM role**.

![AWS CloudFormation](/images/1/00013.png?featherlight=false&width=90pc)

14. Bạn phải clone tài nguyên từ repository:

```
git clone https://github.com/AWS-First-Cloud-Journey/CloudFormation-series.git
```

![AWS CloudFormation](/images/1/00014.png?featherlight=false&width=90pc)




