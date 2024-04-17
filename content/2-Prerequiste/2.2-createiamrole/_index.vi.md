---
title : "Tạo IAM Role"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Tạo IAM Role

Trong bước này chúng ta sẽ tiến hành tạo IAM Role. Trong IAM Role này sẽ được gán policy **AmazonSSMManagedInstanceCore**, đây là policy cho phép máy chủ EC2 có thể giao tiếp với Session Manager.

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/)
2. Ở thanh điều hướng bên trái, click  **Roles**.  

![role](/images/2/35.png)

3. Chọn **AWS service**, sau đó chọn **EC2**.
![role](/images/2/36.png)

4. Tại thanh tìm kiếm, nhập **AmazonSSMManagedInstanceCore** và nhấn enter để tìm kiếm policy này.
    - Click policy **AmazonSSMManagedInstanceCore**.
    - Click **Next**
![role](/images/2/37.png)
5. Đặt tên cho role: ``SSM-Role``
    - Click **Create Role** \.
![role](/images/2/38.png)

Tiếp theo chúng ta sẽ thực hiện kết nối đến các máy chủ EC2 chúng ta đã tạo bằng **Session Manager**.