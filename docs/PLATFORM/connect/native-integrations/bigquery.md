---
title: BigQuery
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To enable BigQuery data transfer, you need to add Lifesight's service account as a Principal in your Google project's IAM and Admin settings with the `BigQuery Data Viewer` role. Lifesight will then set up the BigQuery Data Transfer on our Google Cloud project to pull in data from your BigQuery dataset.

# Steps to Integrate with BigQuery

* Go to IAM & Admin in your Google Cloud Project.
* Click on the Grant Access button.
* In the Add Principals section, enter [lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com.](mailto:lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com.)
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

   <Image align="center" src="https://files.readme.io/ce3ec86ec1ddbf434edaa9ae95238a9d9dbfd89705b2d86ad629ca92d2dafdc8-SCR-20241008-pbyc-2.png" />
3. Click on the BigQuery tile and click on the `Next` button to enter BigQuery details

   <Image align="center" src="https://files.readme.io/52420a2c9c835e814907e729527079a35b26cd3f64cba9ea88be3dd638f24df3-SCR-20241008-pddo-2.png" />
4. Enter the Google Project ID, Dataset ID, and pick the Dataset Region from the dropdown

   <Image align="center" src="https://files.readme.io/dee378b5b2122a97a5465a45e973d70cf72193a45fd61ca4b61589fbec70c89c-SCR-20241008-pdyk-2.png" />
5. Click on `Request for Integration`

Once you've added Lifesight’s service account ([lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com](mailto:lifesight-bigquery-transfer@moda-platform-prd.iam.gserviceaccount.com)) as a Principal with the "BigQuery Data Viewer" role and provided Lifesight with the aforementioned information, Lifesight will set up the Data Transfer to transfer data from your dataset to Lifesight’s.
