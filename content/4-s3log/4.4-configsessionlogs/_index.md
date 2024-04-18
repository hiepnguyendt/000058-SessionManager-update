---
title : "Monitor session logs"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4.4 </b> "
---

#### Monitor session logs

1. Access [System Manager - Session Manager service management console](https://console.aws.amazon.com/systems-manager/session-manager)
    - Click the **Preferences** tab.
    - Click **Edit**.
![S3](/images/2/68.png)

2. Scroll down, at **S3 logging**, 
    - Click **Enable**, for **Send session logs to S3**.
    - Check for **Allow only encrypted S3 buckets**.
    - Click **Choose a bucket name from the list**.
    - Select the S3 bucket you created.
![S3](/images/2/69.png)

3. Scroll down, click **Save** to save the configuration.

4. Access [System Manager - Session Manager service management console](https://console.aws.amazon.com/systems-manager/session-manager)
    - Click **Start session**.
    - Click **Private Windows Instance**.
    - Click **Start session**.

5. Type the command **ipconfig**.
    - Type the command **hostname**.
    - Click **Terminate** to exit the session, click **Terminate** again to confirm.
![S3](/images/2/70.png)


#### Check **Session logs** in **S3**

1. Go to [S3 service management console](https://s3.console.aws.amazon.com/s3/home)
    - Click on the name of the S3 bucket we created for the lab.

2. Click on the object name sessions log
![S3](/images/2/71.png)

3. On the objects detail page, click **Open**.
![S3](/images/2/72.png)

4. Object logs will be opened in a new tab in the browser. You can view the stored commands in session logs.
![S3](/images/2/73.png)