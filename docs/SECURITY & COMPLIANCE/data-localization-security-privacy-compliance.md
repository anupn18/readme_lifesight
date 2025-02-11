---
title: Data localization
excerpt: Store your Lifesight data as per your local privacy laws
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: link
      title: Data Localization information
      url: >-
        https://drive.google.com/file/d/15FhLCsz3ro0WW6W8shnXFxuZN2abFDhK/view?usp=sharing
---
## Overview

Lifesight is committed to providing robust and compliant data management solutions tailored to meet the specific needs of our clients. The platform operates on **Google Cloud server infrastructure**, designed to support data localization and compliance with regional data storage regulations.

This document details how Lifesight sets up and manages localized server infrastructure based on client requirements, ensuring that data is stored in the appropriate geographic region.

<br />

## Data localization at workspace level

Lifesight offers data localization at the workspace level, which means that every client's data can be stored in a specific geographic region based on their preferences and regulatory requirements.

**Workspace-specific BigQuery datasets:**

- For each client, Lifesight sets up a dedicated BigQuery dataset, which serves as the Data Warehouse (DWH) for storing all of the client's data.
- This dataset includes multiple tables that hold various types of data relevant to the client's operations.
- The only exceptions are access-related data and some summarized statistics, which are non-sensitive and may reside outside the main DWH.

<br />

**Regional support and data storage:**

- Data localization is implemented at the workspace level. This means that if a client requires data to be localized, Lifesight will create a separate workspace for each geographic region the client operates in.
- Currently, Lifesight supports data localization in the following regions where we can create BigQuery instances in Google Cloud Platform (GCP):
- United States
- Asia Pacific
- Europe
- Middle East and Africa

<br />

## Implementation process

1. **Client requirement assessment:**

- Lifesight works closely with the client to understand their data localization requirements, including specific regions where data needs to be stored.
- Based on this assessment, Lifesight determines the number of workspaces needed and the appropriate geographic regions for data storage.

2. **Workspace creation and configuration:**

- Separate workspaces are created for each region where data localization is required.
- For each workspace, a dedicated BigQuery dataset is set up within the specified region. This ensures that all data for that workspace is stored within the chosen geographic location.

3. **Data management and compliance:**

- Lifesight ensures that all data within each workspace is managed according to the client’s data governance policies and regional compliance requirements.
- Regular audits and checks are conducted to ensure that data remains localized as per the client’s specifications.

> 📘 Note - Once a specific region is chosen to store workspace data. The client cannot migrate their data to a different region. A client will have to start fresh and create a new workspace to accommodate the new data localization requirements.

<br />

## Benefits

1. **Compliance with regional regulations:**  
   By localizing data storage to specific geographic regions, Lifesight helps clients comply with regional data protection and privacy laws, such as GDPR in Europe, CCPA in the United States.

<!----->

1. **Enhanced data security:**  
   Clients using Lifesight’s localized Google Cloud instance automatically benefit from data security policies and standards offered by Google Cloud.
2. **Optimized performance:**  
   Data localization can lead to improved performance and reduced latency, as data is stored closer to where it is needed and used.

<br />

## Security & privacy compliance

- ISO 27001
- AICPA SOC 2
- GDPR
- CCPA