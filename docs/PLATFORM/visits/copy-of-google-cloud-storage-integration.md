---
title: Amazon S3 Integration
deprecated: false
hidden: true
metadata:
  robots: noindex
---
### Uploading a new AdLog file through Amazon S3:

1. Click Data in the navbar.
2. Click the **Amazon S3** connector card which has the **Visits** tag.

![](https://files.readme.io/a879c6540260adc1376f026810aad1bcb8dbaa27035f6c20f58426235adad820-image.png)

3. You are taken to the list of imported S3 files (Empty list if this is the first upload). Click **Add new Integration** to upload a new s3 file.

![](https://files.readme.io/c8ef28d2a6b1f386869834a9c617f631979db0e8b5639acc26543afe1e666a28-image.png)

**S3 credential modal:**

![](https://files.readme.io/c187269651b53e869548f328a77cdfe0fdf0a508a00c2b3e062f4e6de0cbe40d-image.png)

4. **Details Required:**
   1. **Data Source Name:&#x20;**&#x44;ata Source Name must not contain spaces. Valid characters are `A-Z, a-z, 0-9 and underscore (_)`&#x20;
   2. **Bucket Region:&#x20;**&#x54;he AWS region the bucket is in, for example `us-east-1`.
   3. **Bucket Name:&#x20;**&#x54;he name of the bucket, **without** the s3:// prefi&#x78;**.**
   4. **Secret Token:&#x20;**&#x54;he AWS secret access key paired with the access key ID above. It is shown only once, at the time the key is created, so use the value you saved then. If you no longer have it, generate a new key pair in IAM rather than trying to retrieve the old one.
   5. **Access Key:&#x20;**&#x54;he AWS access key ID of the IAM user that has read access to the bucket. It is the public half of the credential pair and looks something like `AKIAIOSFODNN7EXAMPLE`
   6. **Key Prefix:&#x20;**&#x54;he path to the file inside the bucket, meaning everything after the bucket name.
5. **Understanding Bucket Name and Key Prefix:&#x20;**
   1. A S3 path is made up of two parts: the bucket name and the key prefix.<br /><br />**Example 1: file at the root of the bucket**<br />`s3://lifesight-test/sample_dooh-adlog.csv`<br /><br />**Bucket Name:** `lifesight-test`

      **Key Prefix:** `sample_dooh-adlog.csv`

      <br />**Example 2: file inside a folder**<br />`s3://lifesight-test/adlog/sample_dooh.csv`<br /><br />**Bucket Name:** `lifesight-test`

      **Key Prefix:&#x20;**`adlog/sample_dooh.csv`

      <Callout icon="📘" theme="info">
        The bucket name stays the same in both cases. The key prefix includes any folder path, so when the file sits inside a folder you must include the folder name in the key prefix.
      </Callout>
6. **Required columns:&#x20;**&#x54;he file in the S3 path you provided must contain all of the following columns, spelled exactly as shown. If any column is missing or named differently, the import will fail.<br />

   | Column Name            |
   | ---------------------- |
   | oohid                  |
   | latitude               |
   | longitude              |
   | radius                 |
   | ad_start_time_utc      |
   | ad_play_time           |
   | ad_duration_in_seconds |
   | creative               |
   | lineid                 |
7. **Mapping identifiers:&#x20;**
   1. Columns that match the expected names are mapped to the Lifesight schema automatically, and their status updates to Mapped.
   2. Enable the Primary toggle for the identifier you want to use as the primary key. In most cases it is `oohid`

![](https://files.readme.io/e559813ecc7944303d18916c33078e296a9c716a550ad26ad85a97eb991a461b-image.png)

7. **Importing:**
   1. Click **Connect**. On a successful upload you are redirected to the S3 files list page.
   2. The integration status will show `PROCESSING`.
   3. Once the status changes to `READY`, it means the visits analysis is successful and the insights are ready to be consumed.
