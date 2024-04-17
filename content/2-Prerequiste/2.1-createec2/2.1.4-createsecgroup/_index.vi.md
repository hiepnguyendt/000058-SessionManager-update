---
title : "Tạo các security group"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.1.4 </b> "
---

#### Tạo các security group

Trong bước này chúng ta sẽ tiến hành tạo các security group được sử dụng cho các instance của chúng ta. Các bạn có thể thấy, các securiy group này sẽ không cần phải mở các port truyền thống để **ssh** như port **22** hoặc **remote desktop** thông qua port **3389**.

#### Tạo security group cho Linux instance nằm trong public subnet 

1. Truy cập [giao diện quản trị dịch vụ VPC](https://console.aws.amazon.com/vpc)
    - Click **Security Group**.  
    - Click **Create security group**.
![VPC](/images/2/20.png)

3. Tại mục **Security group name**, điền **SG Public Linux Instance**. 
    - Tại mục **Description**, điền **SG Public Linux Instance**.
    - Tại mục **VPC**, click dấu **X** để chọn lại **Lab VPC** bạn đã tạo cho bài lab này.
![VPC](/images/2/21.png)

4. Giữ nguyên **Outbound rule**, kéo chuột xuống phía dưới.
    - Click **Create security group**.

{{%notice tip%}}
Các bạn có thể thấy, security group chúng ta tạo sử dụng cho Linux public instance sẽ không cần phải mở các port truyền thống để **ssh** như port **22**.
{{%/notice%}}


#### Tạo security group cho Windows instance nằm trong private subnet 

1. Sau khi tạo thành công security group cho Linux instance nằm trong public subnet, click vào link Security Groups để quay trở lại danh sách Security groups.
![VPC](/images/2/22.png)

2. Click **Create security group**.

3. Tại mục **Security group name**, điền **SG Private Windows Instance**. 
    - Tại mục **Description**, điền **SG Private Windows Instance**.
    - Tại mục **VPC**, click dấu **X** để chọn lại **Lab VPC** bạn đã tạo cho bài lab này.
![VPC](/images/2/23.png)

4. Kéo chuột xuống phía dưới.
    - Thêm **Outbound rule** cho phép kết nối TCP 443 tới 10.10.0.0/16 ( CIDR của **Lab VPC** chúng ta đã tạo)
    - Click **Create security group**.
![VPC](/images/2/24.png)

{{%notice tip%}}
Đối với Instance trong private subnet, chúng ta sẽ kết nối tới endpoint của **Session Manager** qua kết nối đã được mã hóa TLS. vì thế chúng ta cần cho phép kết nối chiều ra từ instance của mình tới VPC CIDR thông qua port 443.
{{%/notice%}}


#### Tạo security group cho VPC Endpoint

1. Trong bước này, chúng ta sẽ tạo security group cho VPC Endpoint của **Session Manager**.
2. Sau khi tạo thành công security group cho Windows instance trong private subnet, click vào link Security Groups để quay trở lại danh sách Security groups.
3. Click **Create security group**.
4.  Tại mục **Security group name**, điền **SG VPC Endpoint**. 
    - Tại mục **Description**, điền **SG VPC Endpoint**.
    - Tại mục **VPC**, click dấu **X** để chọn lại **Lab VPC** bạn đã tạo cho bài lab này.
![VPC](/images/2/25.png)

5. Kéo chuột xuống phía dưới.
    - Xóa **Outbound rule**.
![VPC](/images/2/26.png)

6. Thêm **Inbound rule** cho phép TCP 443 đến từ 10.10.0.0/16 ( CIDR của **Lab VPC** chúng ta đã tạo ).
    - Click **Create security group**.
![VPC](/images/2/27.png)

Như vậy chúng ta đã tiến hành xong việc tạo các security group cần thiết cho các EC2 instance và VPC Endpoint.