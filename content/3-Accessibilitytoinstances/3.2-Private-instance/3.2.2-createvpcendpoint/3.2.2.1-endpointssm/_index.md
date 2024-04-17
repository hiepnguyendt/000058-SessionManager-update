---
title : "Create Endpoint ssm"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.2.2.1 </b> "
---


#### Create VPC Endpoint SSM

1. Go to [VPC service management console](https://console.aws.amazon.com/vpc/home)
    - Click **Endpoints**.
    - Click **Create endpoint**.
![Connect](/images/2/46.png)

2. At the **Create endpoint** page.
    - In the **Name tag** field, enter **SSM**.
    - In the **Service Category** section, select **AWS Services**.
    - In the **Service** section, fill the ```.ssm``` in the search bar
      - Then select **Service Name: com.amazonaws.ap-southeast-1.ssm**.
![Connect](/images/2/47.png)

3.  - In the **VPC** section, select **Lab VPC**.
    - Select the first AZ, then select the **Lab Private Subnet** subnet.
![Connect](/images/2/48.png)

4. Scroll down.
    - In the **Security Group** section, select the Security group **SG VPC Endpoint** that we created earlier.
    - In the **Policy** section, select **Full access**.
![Connect](/images/2/49.png)

5. Scroll down.
    - Click **Create endpoint**.
6. We have created the VPC Interface Endpoint for **SSM**.