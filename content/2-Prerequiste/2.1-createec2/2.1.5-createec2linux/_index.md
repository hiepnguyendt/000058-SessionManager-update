---
title : "Create Public instance"
date : "`r Sys.Date()`"
weight : 5
chapter : false
pre : " <b> 2.1.5 </b> "
---

#### Create Public EC2 Linux

You refer to how to create [EC2 Linux](https://000004.awsstudygroup.com/4-launchlinuxinstance/)

1. Go to [EC2 service management console](https://console.aws.amazon.com/ec2/v2/home)
    - Click **Instances**.
    - Click **Launch instances**.
![EC2](/images/2/28.png)
2. In the **Name and tags**
    - Input your name instance: ``Public Linux Instance``
3. On the **Step 1: Choose an Amazon Machine Image (AMI)** page.
    - Click **Select** to select AMI **Amazon Linux 2 AMI**.
![EC2](/images/2/29.png)
4. On the **Instance Type** page.
    - Click on Instance type **t2.micro**.
5. In the **Key Pair (login)**.
    - Click to select **Select an existing key pair**.
    ![EC2](/images/2/33.png)
{{%expand "Click here If you have not an keypair" %}}
  - Click to select **Create a new key pair**.
    - In the **Key pair name** field, enter **aws-key**.
    - Click **Download Key Pair** and save it to your computer.
    - Click **Launch Instances** to create EC2 server.
    ![EC2](/images/2/30.png)
{{% /expand%}}

6. At **Network setting** page
    - In the **VPC** section, select **Lab VPC**.
    - In the **Subnet** section, select **Lab Public Subnet**.
    - In the **Auto-assign Public IP** section, select **Use subnet setting (Enable)**
    - In the **Firewall (security group)**, select **select existing security group**
      - In the **Common security group**, select **SG Pulic Linux Instance**
![EC2](/images/2/31.png)

7. Click **Launch**.

8. Click **View Instances** to return to the list of EC2 instances.
Next, we will do the same to create an EC2 Instance Windows running in the Private subnet.