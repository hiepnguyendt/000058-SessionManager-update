---
title : "Port Forwarding"
date :  "`r Sys.Date()`" 
weight : 5 
chapter : false
pre : " <b> 5. </b> "
---

{{% notice info %}}
**Port Forwarding** là mốt cách thức hữu ích để chuyển hướng lưu lượng mạng từ 1 địa chỉ IP - Port này sang 1 địa chỉ IP - Port khác. Với **Port Forwarding** chúng ta có thể truy cập một EC2 instance nằm trong private subnet từ máy trạm của chúng ta.
{{% /notice %}}

Chúng ta sẽ cấu hình **Port Forwarding** cho kết nối RDP giữa máy của mình với **Private Windows Instance** nằm trong private subnet mà chúng ta đã tạo cho bài thực hành này.

![port-fwd](/images/arc-04.png) 



#### Tạo IAM User có quyền kết nối SSM

1. Truy cập vào [giao diện quản trị dịch vụ IAM](https://console.aws.amazon.com/iamv2/home)
    - Click **Users** , sau đó click **Add users**.
![FWD](/images/2/74.png)

2. Tại trang **Create user**.
    - Tại mục **User name**, điền **Portfwd**.
    - Click **Next**.
![FWD](/images/2/75.png)
3. Tại trang **Set permission** 
   - Chọn **Attach policies directly**
   - Tại thanh tìm kiếm, nhập **ssm**.
   - Click  **AmazonSSMFullAccess**.
   - Click **Next**, click **Next: Reviews**.
   - Click **Create user**.
![FWD](/images/2/76.png)
4. Tạo access key cho **Portfwd** user 
   - Click **Create access key**
   ![FWD](/images/2/77.png)
   - Chọn **Command Line Interface(CLI)**
   - Check box confirmation
   - Click **Next**
![FWD](/images/2/78.png)
   - Click **Download.csv file**
![FWD](/images/2/79.png)
Lưu lại thông tin **Access key ID** và **Secret access key** để thực hiện cấu hình AWS CLI.

#### Cài đặt và cấu hình AWS CLI và Session Manager Plugin 
  
Để thực hiện phần thực hành này, đảm bảo máy trạm của bạn đã cài [AWS CLI]() và [Session Manager Plugin](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager-working-with-install-plugin.html)

Bạn có thể tham khảo thêm bài thực hành về cài đặt và cấu hình AWS CLI [tại đây](https://000011.awsstudygroup.com/).

{{%notice tip%}}
Với Windows thì khi giải nén thư mục cài đặt **Session Manager Plugin** bạn hãy chạy file **install.bat** với quyền Administrator để thực hiện cài đặt.
{{%/notice%}}

#### Thực hiện Portforwarding 

1. Chạy command dưới đây trong **Command Prompt** trên máy của bạn để cấu hình **Port Forwarding**.
    ```
      aws ssm start-session --target (your ID windows instance) --document-name AWS-StartPortForwardingSession --parameters portNumber="3389",localPortNumber="9999" --region (your region) 
    ```
  
  {{%notice tip%}}

  Thông tin **Instance ID** của **Windows Private Instance** có thể tìm được khi bạn xem chi tiết máy chủ EC2 Windows Private Instance.

  {{%/notice%}}

  - Câu lệnh ví dụ

    ```
    C:\Windows\system32>aws ssm start-session --target i-06343d7377486760c --document-name AWS-StartPortForwardingSession --parameters portNumber="3389",localPortNumber="9999" --region ap-southeast-1
    ```

  {{%notice warning%}}
  Nếu câu lệnh của bạn báo lỗi như dưới đây : \
  SessionManagerPlugin is not found. Please refer to SessionManager Documentation here: http://docs.aws.amazon.com/console/systems-manager/session-manager-plugin-not-found\
  Chứng tỏ bạn chưa cài Session Manager Plugin thành công. Bạn có thể cần khởi chạy lại **Command Prompt** sau khi cài **Session Manager Plugin**.
  {{%/notice%}}

2. Kết nối tới **Private Windows Instance** bạn đã tạo bằng công cụ **Remote Desktop** trên máy trạm của bạn.
    - Tại mục Computer: điền **localhost:9999**.
![FWD](/images/2/80.png)


3. Quay trở lại giao diện quản trị của dịch vụ System Manager - Session Manager.
    - Click tab **Session history**.
    - Chúng ta sẽ thấy các session logs với tên Document là **AWS-StartPortForwardingSession**.
![FWD](/images/2/81.png)


Chúc mừng bạn đã hoàn tất bài thực hành hướng dẫn cách sử dụng Session Manager để kết nối cũng như lưu trữ các session logs trong S3 bucket. Hãy nhớ thực hiện bước dọn dẹp tài nguyên để tránh sinh chi phí ngoài ý muốn nhé.