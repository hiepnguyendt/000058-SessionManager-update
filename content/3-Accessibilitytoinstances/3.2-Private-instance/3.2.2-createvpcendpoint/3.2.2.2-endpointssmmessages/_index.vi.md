---
title : "Tạo Endpoint ssmmessages"
date :  "`r Sys.Date()`" 
weight : 2
chapter : false
pre : " <b> 3.2.2.2 </b> "
---


#### Tạo VPC Endpoint SSMMESSAGES

1. Truy cập đến [giao diện quản trị của dịch vụ VPC](https://console.aws.amazon.com/vpc/home)
    - Click **Endpoints**.
    - Click **Create endpoint**.
  
2. Tại trang **Create endpoint**.
    - Tại mục **Name tag** điền **SSMMESSAGES**.
    - Tại mục **Service Category** chọn **AWS Services**.
    - Tại mục **Services**,
      - Tại thanh **Search** nhập: **.ssmmessages**, sau đó chọn **Service Name: com.amazonaws.ap-southeast-1.ssmmessages**.
![Connect](/images/2/50.png)

3.  - Tại mục **VPC**, chọn **Lab VPC**.
    - Chọn AZ đầu tiên, sau đó chọn subnet **Lab Private Subnet**.
    - Tại mục **Security Group**, chọn Security group **SG VPC Endpoint** mà chúng ta đã tạo trước đó.
    - Tại mục **Policy**, chọn **Full access**
![Connect](/images/2/51.png)

4. Kéo chuột xuống dưới cùng.
    - Click **Create endpoint**.

5. Chúng ta đã tạo xong VPC Interface Endpoint  **SSMMESSAGES**.
