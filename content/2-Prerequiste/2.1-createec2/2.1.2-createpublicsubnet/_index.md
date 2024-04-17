---
title : "Create Public Subnet"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.1.2 </b> "
---

#### Create Public Subnet

1. Click **Subnets**.
      - Click **Create subnet**.
![VPC](/images/2/3.png)

2. At the **Create subnet** page.
    - In the **VPC ID** section, click **Lab VPC**.
    - In the **Subnet name** field, enter **Lab Public Subnet**.
    - In the **Availability Zone** section, select the first Availability zone.
    - In the field **IPv4 CIRD block** enter **10.10.1.0/24**.
![VPC](/images/2/4.png)

3. Scroll to the bottom of the page, click **Create subnet**.

4. Click **Lab Public Subnet**.
    - Click **Actions**.
    - Click **Edit subnet settings**.
![VPC](/images/2/5.png)

5. Click **Enable auto-assign public IPv4 address**.
  ![VPC](/images/2/6.png)

6. Click **Internet Gateways**.
    - Click **Create internet gateway**.
![VPC](/images/2/7.png)

7. At the **Create internet gateway** page.
    - In the **Name tag** field, enter **Lab IGW**.
    - Click **Create internet gateway**.
![VPC](/images/2/8.png)

8. After successful creation, click **Actions**.
    - Click **Attach to VPC**.
![VPC](/images/2/9.png)

9. At the **Attach to VPC** page.
    - In the **Available VPCs** section, select **Lab VPC**.
    - Click **Attach internet gateway**.
    - Check the successful attaching process as shown below.
![VPC](/images/2/10.png)

10. Next we will create a custom route table to assign to **Lab Public Subnet**.
    - Click **Route Tables**.
    - Click **Create route table**.
![VPC](/images/2/11.png)

11. At the **Create route table** page.
    - In the **Name** field, enter **Lab Publicrtb**.
    - In the **VPC** section, select **Lab VPC**.
    - Click **Create route table**.
![VPC](/images/2/12.png)
12. After creating the route table successfully.
    - Click **Edit routes**.
![VPC](/images/2/13.png)

13. At the **Edit routes** page.
    - Click **Add route**.
    - In the **Destination** field, enter 0.0.0.0/0
    - In the **Target** section, select **Internet Gateway** and then select **Lab IGW**.
    - Click **Save changes**.
![VPC](/images/2/14.png)

14. Click the **Subnet associations** tab.
    - Click **Edit subnet associations** to proceed with the associate custom route table we just created in **Lab Public Subnet**.
![VPC](/images/2/15.png)

15. At the **Edit subnet associations** page.
    - Click on **Lab Public Subnet**.
    - Click **Save associations**.
![VPC](/images/2/16.png)

16. Check that the route table information has been associated with **Lab Public Subnet** and the internet route information has been pointed to the Internet Gateway as shown below.
![VPC](/images/2/17.png)