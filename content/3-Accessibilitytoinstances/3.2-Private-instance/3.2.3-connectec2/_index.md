---
title : "Connect to instance"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.2.3 </b> "
---


#### Assign IAM role and restart EC2 instance.

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Private Windows Instance**.
    - Click **Actions**.
    - Click **Security**.
    - Click **Modify IAM Role**.
![Connect](/images/2/54.png)

2. At the **Modify IAM Role** page.
    - In the IAM role section, select **SSM-Role**.
    - Click **Update IAM role**.
![Connect](/images/2/55.png)

3. Click **Private Windows Instance**.
    - Click **Instance state**.
    - Click **Reboot instance** to restart, then click **Reboot** to confirm.
![Connect](/images/2/56.png)
{{% notice note %}}
Please wait 5 minutes before doing the next step.
 {{% /notice %}}

#### Connect to the private EC2 instance.

1. Go to [System Manager - Session Manager service management console](https://console.aws.amazon.com/systems-manager/session-manager)
    - Click **Start session**.
  
2. Click **Private Windows Instance**.
    - Click **Start session**.
![Connect](/images/2/57.png)
3. Type **ipconfig** command to check the IP address information of **Private Windows Instance** as shown below.
    ![Connect](/images/2/58.png)