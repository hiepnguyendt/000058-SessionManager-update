---
title : "Create Endpoint ssmmessages"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2.2.2 </b> "
---


#### Create VPC Endpoint SSMMESSAGES

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
    - Click **Endpoints**.
    - Click **Create endpoint**.
  
2. At the **Create endpoint** page.
    - In the **Name tag** field, enter **SSMMESSAGES**.
    - In the **Service Category** section, select **AWS Services**.
    - In the **Services** section,
      - In the **Search** field enter: ```.ssmmessages``` then select **Service Name: com.amazonaws.ap-southeast-1.ssmmessages**.
![Connect](/images/2/50.png)

3.  - In the **VPC** section, select **Lab VPC**.
    - Select the first AZ, then select the **Lab Private Subnet** subnet.
    - In the **Security Group** section, select the Security group **SG VPC Endpoint** that we created earlier.
    - In the **Policy** section, select **Full access**
![Connect](/images/2/51.png)
4. Scroll down.
    - Click **Create endpoint**.

5. We have created the VPC Interface Endpoint **SSMMESSAGES**.