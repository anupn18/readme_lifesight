---
title: CSV Import
deprecated: false
hidden: true
metadata:
  robots: index
---
### Uploading a new AdLog file:

1. Click Data in the navbar.
2. Click the **Import CSV** connector card.&#x20;

   <Callout icon="📘" theme="info">
     <br />This is a generic CSV importer used for both the Visits use case and other use cases on the platform.
   </Callout>

![](https://files.readme.io/ff3cb33e413be063d23c3fb7556557bb997995ef079c0d9bc26ab378a01895e1-image.png)

3. What happens next depends on whether the workspace already has CSVs:
   1. **First CSV upload:&#x20;**&#x49;f no CSV has been uploaded yet (Visits or otherwise), the upload popup opens directly.
   2. **CSVs already uploaded:&#x20;**&#x59;ou are taken to the list of imported CSVs. Click Add CSV to open the same popup.

**List of uploaded CSVs:**

![](https://files.readme.io/4cb78b33aa2bedd9ff1588c8cb7dc22345c0d89de0e7269adf701c5922feb359-image.png)

<br />

**Modal for CSV ingestion:**

![](https://files.readme.io/18ea261802d5c4e4ca83c3596b578f83e438d72bd470f873058d162aec7b0002-image.png)

<br />

4. **File naming:&#x20;**&#x46;ile names must not contain spaces. Valid characters are `A-Z, a-z, 0-9 and underscore (_)`&#x20;
5. **Required columns:&#x20;**&#x59;our CSV must contain all of the following columns, spelled exactly as shown. If any column is missing or named differently, the import will fail.<br />


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
6. **Mapping identifiers:&#x20;**
   1. Columns that match the expected names are mapped to the Lifesight schema automatically, and their status updates to Mapped.
   2. Optionally, enable the Primary toggle for the identifier you want to use as the primary key.

![](https://files.readme.io/e30aface47c5cb2a0c7fb70e3b02444f960d6543f4de7ac77167a8a3a546d0b6-image.png)

<br />

7. **Importing:**
   1. Click **Import**. On a successful upload you are redirected to the CSV list page.
   2. The integration status will show `PROCESSING`.
   3. Once the status changes to `READY`, it means the visits analysis is successful and the insights are ready

![](https://files.readme.io/a473b9bed034d6094c997be15a1bf1310e3b02703da988ffc6f38d4e837a101b-image.png)

<br />

<Callout icon="📘" theme="info">
  CSVs ingested for the Visits use case show a Visits tag next to the integration name.
</Callout>