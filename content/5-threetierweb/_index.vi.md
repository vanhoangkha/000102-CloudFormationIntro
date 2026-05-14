---
title : "Triển khai Three-Tier Architecture"
date: 2024-01-01
weight : 5
chapter : false
pre : " <b> 5. </b> "
---

#### Triển khai Three-Tier Architecture

Kiến trúc 3 lớp cung cấp một khung việc tổ chức tổng quát cho việc triển khai các ứng dụng client/server truyền thống thành ba lớp logic: lớp Web, lớp Ứng dụng và lớp Cơ sở dữ liệu. Người dùng cuối tương tác với lớp Web (ví dụ: ứng dụng di động, trang web, v.v.), lớp này cung cấp giao diện người dùng cho họ để xem, sửa đổi hoặc gửi thông tin. Lớp Ứng dụng chịu trách nhiệm xử lý các yêu cầu được thực hiện bởi người dùng. Nó hỗ trợ dịch các hành động của người dùng thành logic kinh doanh cho phép xử lý dữ liệu bởi các chương trình. Cuối cùng, lớp Cơ sở dữ liệu hoặc lớp Dữ liệu là nơi lưu trữ và quản lý thông tin được xử lý bởi ứng dụng.

#### Triển khai Web Tier

- 2 public subnets
- Public route table
- Internet Gateway & NAT Gateway
- Internet facing Application Load Balancer với một Security Group cho phép lưu lượng đi ra Internet.
- Ít nhất 2 EC2 instance với Auto Scaling Group.
- EC2 Security Group cho phép lưu lượng đi đến Web Tier Application Load Balancer
- Boot strap static web page.
- Tạo public route table và liên kết với 2 public subnets.

#### Triển khai Application Tier

- 2 private subnets
- Private route table
- Internal Application Load Balancer với một Security Group cho phép đi từ EC2 instances trong Web Tier
- Ít nhất 2 EC2 instance với Auto Scaling Group.
- EC2 Security Group cho phép inbound lưu lượng đi đến  Application Tier Application Load Balancer
- Liên kết với private route table

#### Triển khai Database Tier

- 2 private subnets
- Public route table
- MySql RDS Database với Multi AZ standby instance
-  Database Security Group cho phép lưu lượng từ MySQL đến  Application Server Security Group


#### Triển khai Bastion Host

- 3 public subnet
- Public route table
- EC2 instance
- EC2 Security Group cho phép SSH từ Internet
- Cho phép Bastion Host EC2 instance Security Group truy cập tài nguyên trong Web, Application, và Database Tier 

#### Nội dung chính:

1. [Triển khai CloudFormation Stack]()
2. [Kiểm tra truy cập vào Web Tier]()
3. [Kiểm tra truy cập vào Application Tier]()
4. [Kiểm tra Database Tier]()


