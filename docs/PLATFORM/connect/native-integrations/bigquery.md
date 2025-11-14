---
title: BigQuery
excerpt: Integrate Google BigQuery to pull in Marketing data from your data warehouse
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[Google BigQuery](https://cloud.google.com/bigquery) is a fully managed, serverless data warehouse that enables scalable analysis of large datasets using SQL. It is widely used by data analysts and engineers for storing, querying, and processing structured data.

The Lifesight–BigQuery integration allows you to connect your datasets stored in BigQuery to the platform. Once integrated, Lifesight can ingest your selected dataset tables to unify them with other marketing and business data, enabling comprehensive attribution and measurement.

## Data Being Brought into Lifesight

Lifesight does not automatically ingest all data from your BigQuery project. Instead, it only reads from the **specific tables defined by you during setup**.

This ensures:

* Full control over which datasets and tables are exposed to Lifesight.
* Compliance with your organization’s data governance and privacy policies.
* Flexibility to integrate only the data relevant for attribution, MMM, or reporting use cases.

To enable BigQuery data transfer, you need to add Lifesight's service account as a Principal in your Google project's IAM and Admin settings with the **BigQuery Data Viewer** role. Lifesight will then set up the BigQuery Data Transfer on our Google Cloud project to pull in data from your BigQuery dataset.

<Embed typeOfEmbed="youtube" url="https://www.youtube.com/watch?v=yQ-57R4oNig" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252FyQ-57R4oNig%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253DyQ-57R4oNig%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252FyQ-57R4oNig%252Fhqdefault.jpg%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22640%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" href="https://www.youtube.com/watch?v=yQ-57R4oNig" providerUrl="https://www.youtube.com/" providerName="YouTube" />

<br />

# Steps to Integrate with BigQuery

* Go to IAM & Admin in your Google Cloud Project.
* Click on the Grant Access button.
* In the Add Principals section, enter `lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com.`
* In the Assign Roles section, select the BigQuery Data Viewer role from the Roles dropdown.
* Click on Save.
* Verify that the Principal was added successfully.

Completing these steps will allow Lifesight to read data from your datasets. Lifesight also need three additional pieces of information from you:

1. The Project ID in which the dataset exists,
2. The Dataset ID, and
3. The Dataset Region (the region in which the dataset resides)

To finish the integration process, click on the BigQuery tile in

1. Navigate to the Integrations tab in the left-hand menu bar.
2. In the search field, type in "BigQuery" to locate the integration for this application.

   <Image align="center" border={false} src="https://files.readme.io/ce3ec86ec1ddbf434edaa9ae95238a9d9dbfd89705b2d86ad629ca92d2dafdc8-SCR-20241008-pbyc-2.png" />
3. Click on the BigQuery tile and click on the **Next** button to enter BigQuery details

   <Image align="center" border={false} src="https://files.readme.io/52420a2c9c835e814907e729527079a35b26cd3f64cba9ea88be3dd638f24df3-SCR-20241008-pddo-2.png" />
4. Enter the Google Project ID, Dataset ID, and pick the Dataset Region from the dropdown

   <Image align="center" border={false} src="https://files.readme.io/dee378b5b2122a97a5465a45e973d70cf72193a45fd61ca4b61589fbec70c89c-SCR-20241008-pdyk-2.png" />
5. Click on **Request for Integration**

Once you've added Lifesight’s service account `lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com` as a Principal with the "BigQuery Data Viewer" role and provided Lifesight with the aforementioned information, Lifesight will set up the Data Transfer to transfer data from your dataset to Lifesight’s.