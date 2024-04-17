---
title : "Tạo Private Windows EC2"
date :  "`r Sys.Date()`" 
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

#### Tạo Private EC2 Windows

Bạn tham khảo cách tạo [EC2 Windows](https://000004.awsstudygroup.com/3-launchwindowsinstance/)

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Instances**.
    - Click **Launch instances**.
2. Tại mục **Name and tags**
    - Đặt tên cho instance: ``Private Windows Instance`` 
3. Tại trang **Amazon Machine Image (AMI)**.
    - Kéo chuột xuống phía dưới.
    - Click **Select** để lựa chọn AMI **Microsoft Windows Server 2019 Base**.
![EC2](/images/2/32.png)

4. Tại mục **Instance Type**.
    - Click chọn Instance type **t2.micro**.
5. Tại mục **Key Pair (login)**.
    - Click chọn **key pair bạn đã tạo trước đó**.
![EC2](/images/2/33.png)
6. Tại mục **Network setting**
    - Tại mục **Network** chọn **Lab VPC**.
    - Tại mục **Subnet** chọn **Lab Private Subnet**.
    - Tại mục **Auto-assign Public IP** chọn **Use subnet setting (Disable)**
    - Tại mục **Firewall (security group)**, chọn **select existing security group**
      - Tại mục **Common security group**, chọn **SG Private Windows Instance**
![EC2](/images/2/34.png)

7. Click **Launch Instances** để tạo máy chủ EC2.

8. Click **View Instances** để quay lại danh mục EC2 instances.
Tiếp theo chúng ta sẽ tiến hành tạo các IAM Role để phục vụ cho Session Manager.