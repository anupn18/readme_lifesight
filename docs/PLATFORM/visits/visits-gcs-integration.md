---
title: Google Cloud Storage Integration
deprecated: false
hidden: true
metadata:
  robots: index
---
### Uploading a new AdLog file through Google Cloud Storage:

1. Click Data in the navbar.
2. Click the **Google Cloud Storage** connector card.&#x20;

![](https://files.readme.io/e428515f757a748d5fb272eab941ebd33501aaa39e399dede8d47507406b0815-image.png)

3. You are taken to the list of imported GCS files (Empty list if this is the first upload). Click **Add new Integration** to upload a new GCS file.

![](https://files.readme.io/52be09c3af008644411e5f2a8fdf969196df15f1d3792eb1c50c5f70f6d9f6d0-image.png)

**GCS credential modal:**

![](https://files.readme.io/ba4a7a2adb571bb3a373966353ea65cb57c8381afac95471101914a73b740931-image.png)

4. **Details Required:**
   1. **Data Source Name:&#x20;**&#x44;ata Source Name must not contain spaces. Valid characters are `A-Z, a-z, 0-9 and underscore (_)`&#x20;
   2. **Bucket Region:&#x20;**&#x54;he region your GCS bucket is hosted in.
   3. **Bucket Name:&#x20;**&#x54;he name of the bucket, **without the gs\:// and key prefix.**
   4. **GCS Credential (JSON File):&#x20;**&#x41; service account key with permission to read the file. You can either upload the JSON file or paste the JSON content directly into the field.
   5. **Key Prefix:&#x20;**&#x54;he path to the file inside the bucket, meaning everything after the bucket name.
5. **Understanding Bucket Name and Key Prefix:&#x20;**
   1. A GCS path is made up of two parts: the bucket name and the key prefix.<br /><br />**Example 1: file at the root of the bucket**<br />`gs://lifesight-test/sample_dooh-adlog.csv`<br /><br />**Bucket Name:** `lifesight-test`**Key Prefix:** `sample_dooh-adlog.csv`

      <br />**Example 2: file inside a folder**<br />`gs://lifesight-test/adlog/sample_dooh.csv`<br />**Bucket Name:** `lifesight-test`**Key Prefix:&#x20;**`adlog/sample_dooh.csv`

      <Callout icon="📘" theme="info">
        The bucket name stays the same in both cases. The key prefix includes any folder path, so when the file sits inside a folder you must include the folder name in the key prefix.
      </Callout>
6. **Required columns:&#x20;**&#x59;our CSV must contain all of the following columns, spelled exactly as shown. If any column is missing or named differently, the import will fail.<br />

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


<Image src="https://files.readme.io/a2bdeb40b06863e7331aa5c6a00842a66d635183b7c7cf5376e563cd65350694-image.png" align="center" />


7. **Importing:**
   1. Click **Connect**. On a successful upload you are redirected to the GCS file list page.
   2. The integration status will show `PROCESSING`.
   3. Once the status changes to `READY`, it means the visits analysis is successful and the insights are ready
