---
title: Amazon S3
excerpt: Integrate Amazon S3 on Lifesight
deprecated: false
hidden: false
metadata:
  robots: index
---
Amazon S3 (Simple Storage Service) is a secure and highly scalable object storage service. The Lifesight Amazon S3 integration allows you to connect directly to your S3 bucket to pull any custom dataset into the Unified Marketing Measurement (UMM) platform.

This feature enables you to bring your unique business data into Lifesight for a truly comprehensive view of marketing performance.

<br />

### **Setup Instructions in AWS**

To connect your S3 bucket securely, we will first create a dedicated user in your AWS account with the minimum permissions required for Lifesight to read your data. This process involves creating a permissions policy, creating a user, and generating a unique set of access keys.

<br />

#### **Part A: Create a Limited Permission IAM Policy**

This policy explicitly grants Lifesight read only access to a specific S3 bucket.

1. Open your Amazon IAM console in your AWS account.
2. Navigate to **Policies** in the left side menu, then click **Create Policy**.
3. Select the **JSON** tab.
4. Copy the entire policy text below and paste it into the JSON editor, replacing the existing content. Be sure to replace `{your-bucket-name}` with the actual name of your S3 bucket.

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
        "Effect": "Allow",
        "Action": [
                "s3:GetBucketLocation",
                "s3:GetObject",
                "s3:ListBucket"
        ],
        "Resource": [
                "arn:aws:s3:::{your-bucket-name}/*",
                "arn:aws:s3:::{your-bucket-name}"
        ]
        }
    ]
}
```

5. Click **Next: Tags**, then **Next: Review**.
6. For the **Name**, enter something descriptive like `Lifesight-S3-Read-Access-Policy`.
7. Click **Create policy** to save.

<br />

#### **Part B: Create a Dedicated IAM User**

Now, you will create a user that will be assigned the policy you just created.

1. In the IAM console, navigate to **Users** in the left side menu, then click **Add users**.
2. Enter a **User name**, for example `lifesight-s3-integration-user`.
3. Click **Next**.
4. On the **Set permissions** page, select **Attach policies directly**.
5. In the search bar, type the name of the policy you created in Part A (e.g., `Lifesight-S3-Read-Access-Policy`) and check the box next to it.
6. Click **Next**, then click **Create user**.

<br />

#### **Part C: Generate an Access Key and Secret**

This is the final step in AWS, where you generate the credentials you will use in the Lifesight platform.

1. From the list of users, click on the name of the user you just created.
2. Navigate to the **Security credentials** tab.
3. Scroll down to the **Access keys** section and click **Create access key**.
4. For the use case, select **Third party service** and click **Next**.
5. Click **Create access key**.
6. You will now see the **Access key ID** and the **Secret access key**.

***

## **Steps to Integrate in Lifesight**

With your AWS credentials prepared, you can now complete the connection within the Lifesight platform.

1. Navigate to the **Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**Amazon S3**" to locate the integration tile.
3. Click on the **Amazon S3** tile. A connection modal will appear.
4. Carefully enter the **Access Key ID** you saved from AWS.
5. Enter the corresponding **Secret Access Key**.
6. Select your **S3 Bucket Region** from the dropdown menu.
7. Enter the exact **S3 Bucket Name** (this must match the one in your IAM policy).
8. Click **Connect** to finalize the integration.
