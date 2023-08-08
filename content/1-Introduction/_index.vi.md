---
title : "Giới thiệu"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---

#### Giới thiệu 

Trong phạm vi workshop series này, chúng ta sẽ giới thiệu các khái niệm cơ bản và lợi ích của IaC (Infrastructure as Code), so sánh các framework IaC, và các bước để làm quen với IaC.

**IaC** là một phương pháp quản lý hạ tầng trong đó việc triển khai và quản lý cơ sở hạ tầng được thực hiện thông qua mã nguồn. Một trong những lợi ích lớn nhất của IaC là tăng năng suất làm việc.

Một số lợi ích của IaC bao gồm đơn giản hóa việc quản lý hạ tầng, khả năng sử dụng lại mã nguồn, và theo dõi sự thay đổi của hạ tầng. Ví dụ, thay vì phải tạo, cấu hình và kết nối các dịch vụ trong hạ tầng một cách thủ công, bạn có thể sử dụng các mẫu CloudFormation để tự động tạo và kết nối các dịch vụ này với nhau. Khi không cần sử dụng nữa, bạn chỉ cần xóa mẫu này từ CloudFormation. Bạn cũng có thể sử dụng mẫu này để triển khai dịch vụ ở nhiều region, nhiều tài khoản khác nhau và theo dõi sự thay đổi của hạ tầng từ CloudFormation.

Ngoài ra, IaC còn mang lại nhiều lợi ích khác như tính an toàn. Ví dụ, thay vì viết policy IAM để cho phép một Lambda function có thể đọc dữ liệu từ một S3 Bucket, khi sử dụng CDK (Cloud Development Kit), bạn có thể viết **bucket.grantReadOnly**(lambdaFunction). CDK sẽ tự động tạo ra policy với các best practice.

Một khía cạnh quan trọng khác của IaC là vai trò trong CI/CD và DevOps. IaC là một yêu cầu quan trọng trong các công việc liên quan đến DevOps, nơi triển khai và kiểm thử hạ tầng tự động trở nên khó khăn mà không sử dụng IaC.

#### Các framework IaC

Hiện có nhiều framework IaC khác nhau từ năm 2011 đến nay, bao gồm CloudFormation, CloudFormation SAM, CDK, CDK8S, được phát triển và hỗ trợ bởi AWS. Các framework này có các tính năng chung như khai báo hạ tầng bằng mã nguồn và theo dõi sự thay đổi của hạ tầng. Tuy nhiên, các framework này có sự khác nhau về công cụ triển khai hạ tầng và tích hợp với AWS. CloudFormation, SAM và CDK đều triển khai hạ tầng thông qua dịch vụ CloudFormation. Terraform, Pulumi và Serverless có các công cụ triển khai riêng và không sử dụng CloudFormation.

Để bắt đầu với IaC, bạn có thể làm quen với CloudFormation template bằng cách khai báo hạ tầng, tham số và bản đồ. Bạn cũng có thể quản lý sự thay đổi cấu hình và tạo các bản cập nhật thông qua CloudFormation. Ngoài ra, bạn cũng có thể triển khai cùng một stack trên nhiều tài khoản và region khác nhau bằng cách sử dụng StackSet.

#### Các bước để làm quen với IaC

Để làm quen với CDK, bạn cần hiểu các khái niệm trừu tượng như Construct, Stack, Props, Interface, Type và ID. Bạn cần hiểu và kiểm soát sự phụ thuộc giữa các Stack và quản lý sự thay đổi hạ tầng khi cập nhật Stack. Bạn cũng có thể phân chia một kiến trúc thành các Stack nhỏ hơn và triển khai song song nhiều Stack.

Cuối cùng, bạn có thể xây dựng và tích hợp IaC vào quy trình CI/CD.
