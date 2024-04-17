---
title : "Tạo Public Linux EC2"
date :  "`r Sys.Date()`" 
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

#### Tạo Public EC2 Linux

Bạn tham khảo cách tạo [EC2 Linux](https://000004.awsstudygroup.com/4-launchlinuxinstance/)

1. Truy cập [giao diện quản trị dịch vụ EC2](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Instances**.
    - Click **Launch instances**.
![EC2](/images/2/28.png)
2. Tại mục **Name and tags**
    - Đặt tên cho instance: ``Public Linux Instance``
3. Tại mục **Amazon Machine Image (AMI)**.
    - Click **Select** để lựa chọn AMI **Amazon Linux 2 AMI**.
![EC2](/images/2/29.png)

4. Tại mục **Instance Type**.
    - Click chọn Instance type **t2.micro**.
5. Tại mục **Key Pair (login)**.
    - Click chọn **key pair bạn đã tạo trước đó**.
![EC2](/images/2/33.png)
{{%expand "Click vào đây nếu bạn chưa tạo AWS Keypair" %}}
  - Click vào **Create a new key pair**.
    - Tại mục **Key pair name** điền **aws-key**.
    - Click **Download Key Pair** và lưu xuống máy tính của bạn.
    - Click **Launch Instances** để tạo máy chủ EC2.
    ![EC2](/images/2/30.png)
{{% /expand%}}
6. Tại mục **Network setting**
    - Tại mục **Network** chọn **Lab VPC**.
    - Tại mục **Subnet** chọn **Lab Public Subnet**.
    - Tại mục **Auto-assign Public IP** chọn **Use subnet setting (Enable)**
    - Tại mục **Firewall (security group)**, chọn **select existing security group**
      - Tại mục **Common security group**, chọn **SG Pulic Linux Instance**
![EC2](/images/2/31.png)

7. Click **Launch**.
8. Click **View Instances** để quay lại danh mục EC2 instances.
Tiếp theo chúng ta sẽ thực hiện tương tự để tạo 1 EC2 Instance Windows chạy trong Private subnet.