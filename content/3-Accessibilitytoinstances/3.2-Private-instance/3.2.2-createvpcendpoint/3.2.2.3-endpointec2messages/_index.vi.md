---
title : "Tạo Endpoint ec2messages"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 3.2.2.3 </b> "
---


#### Tạo VPC Endpoint EC2MESSAGES

1. Truy cập đến [giao diện quản trị của dịch vụ VPC](https://console.aws.amazon.com/vpc/home)
    - Click **Endpoints**.
    - Click **Create endpoint**.
  
2. Tại trang **Create endpoint**.
    - Tại mục **Name tag** điền **EC2MESSAGES**.
    - Tại mục **Service Category** chọn **AWS Services**.
    - Tại mục **Services**,
    - Tại thanh **Search** nhập: ```.ec2messages```, sau đó chọn **Service Name: com.amazonaws.ap-southeast-1.ec2messages**.
![Connect](/images/2/52.png)

3.  - Tại mục **VPC**, chọn **Lab VPC**.
    - Chọn AZ đầu tiên, sau đó chọn subnet **Lab Private Subnet**.
    - Tại mục **Security Group**, chọn Security group **SG VPC Endpoint** mà chúng ta đã tạo trước đó.
![Connect](/images/2/53.png)

4. Kéo chuột xuống dưới.
    - Tại mục **Policy**, chọn **Full access**
    - Click **Create endpoint**.

6. Chúng ta đã tạo xong VPC Interface Endpoint  **EC2MESSAGES**.

