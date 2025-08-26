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

### **Use Case: Unifying Custom Datasets for Holistic Measurement**

By bringing in your own data via S3, you can significantly enrich your Marketing Mix Models (MMM) and Causal Attribution analyses. This allows you to measure the impact of marketing on a wider range of business outcomes and account for external factors.

### **Prerequisites: Gathering Your S3 Credentials**

Before you begin the integration, you must have four pieces of information ready from your Amazon Web Services account:

* **Access Key ID**
* **Secret Access Key**
* **S3 Bucket Region** (e.g., us east 1)
* **S3 Bucket Name**

> **Security Best Practice**
> For enhanced security, we strongly recommend creating a dedicated IAM (Identity and Access Management) user in your AWS account. This user should be granted specific, read only permissions for the target S3 bucket (`s3:GetObject` and `s3:ListBucket`). Using credentials from a limited access IAM user instead of your root account credentials is a safer practice that minimizes risk.


### **Steps to Integrate Amazon S3**

Connecting your S3 bucket is a straightforward configuration process.

1. Navigate to the **Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**Amazon S3**" to locate the integration tile.
3. Click on the **Amazon S3** tile. A connection modal will appear.
4. Carefully enter your **Access Key ID**.
5. Enter the corresponding **Secret Access Key**.
6. Select your **S3 Bucket Region** from the dropdown menu.
7. Enter the exact **S3 Bucket Name**.
8. Click **Connect** to finalize the integration.
