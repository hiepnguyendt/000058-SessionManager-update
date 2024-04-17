---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Create IAM Role

In this step, we will proceed to create IAM Role. In this IAM Role, the policy **AmazonSSMManagedInstanceCore** will be assigned, this is the policy that allows the EC2 server to communicate with the Session Manager.

1. Go to [IAM service administration interface](https://console.aws.amazon.com/iamv2/)
2. In the left navigation bar, click **Roles**, then Click **Create role**.
![role](/images/2/35.png)

3. Select **AWS service** then **EC2**.
![role](/images/2/36.png)

4. In the Search box, enter **AmazonSSMManagedInstanceCore** and press Enter to search for this policy.
    - Click the policy **AmazonSSMManagedInstanceCore**.
    - Click **Next**
![role](/images/2/37.png)
5. Name the Role **SSM-Role** in Role Name
    - Click **Create Role** \.
![role](/images/2/38.png)

Next, we will make the connection to the EC2 servers we created with **Session Manager**.