---
title : "Create Private Instance"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 2.1.6 </b> "
---

#### Create Private EC2 Windows

You refer to how to create [EC2 Windows](https://000004.awsstudygroup.com/3-launchwindowsinstance/)

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Instances**.
    - Click **Launch instances**.  
2. In the **Name and tags**
    - Input your name instance: ``Private Windows Instance``  
3. On the **Amazon Machine Image (AMI)** page.
    - Drag the mouse down.
    - Click **Select** to select AMI **Microsoft Windows Server 2019 Base**.
![EC2](/images/2/32.png)

4. On the **Instance Type** page.
    - Click on Instance type **t2.micro**.
5. In the **Key Pair (login)**.
    - Click to select **Select an existing key pair**.
![EC2](/images/2/33.png)

6. At **Network setting** page
    - In the **VPC** section, select **Lab VPC**.
    - In the **Subnet** section, select **Lab Private Subnet**.
    - In the **Auto-assign Public IP** section, select **Use subnet setting (Disable)**
    - In the **Firewall (security group)**, select **select existing security group**
      - In the **Common security group**, select **SG Private Windows Instance**
![EC2](/images/2/34.png)


7. Click **Launch**.
8. Click **View Instances** to return to the list of EC2 instances.
Next, we will proceed to create IAM Roles to serve the Session Manager.