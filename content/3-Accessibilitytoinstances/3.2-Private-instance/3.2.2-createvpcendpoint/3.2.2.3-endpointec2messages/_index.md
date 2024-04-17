---
title : "Create Endpoint ec2messages"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.2.2.3 </b> "
---


#### Create VPC Endpoint EC2MESSAGES

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
    - Click **Endpoints**.
    - Click **Create endpoint**.
  
2. At the **Create endpoint** page.
    - In the **Name tag** field, enter **EC2MESSAGES**.
    - In the **Service Category** section, select **AWS Services**.
    - In the **Services** section,
      - In the field **Service Name** enter: ```.ec2messages``` then select **Service Name: com.amazonaws.ap-southeast-1.ec2messages**.
![Connect](/images/2/52.png)

3.  - In the **VPC** section, select **Lab VPC**.
    - Select the first AZ, then select the **Lab Private Subnet** subnet.
    - In the **Security Group** section, select the Security group **SG VPC Endpoint** that we created earlier.
![Connect](/images/2/53.png)

4. Scroll down.
    - In the **Policy** section, select **Full access**
    - Click **Create endpoint**.

5. We have created the VPC Interface Endpoint **EC2MESSAGES**.