---
title: How to build a Causal Inference model
excerpt: >-
  Create your first Causal Model in minutes and estimate the incremental lift
  without running any experiments
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To begin creating a model:

1. Click on the “Create Model” button on the Causal Inference page.
2. You can create a model by uploading your data in a CSV. The dataset is required to contain values of the treatment, outcome, and all common causes.
3. To upload your custom dataset, select the option labeled "Upload your data." Either click on "click to upload" or drag and drop the file into the designated area.

![](https://files.readme.io/7bb43d188fa0dbad3f8434525f97d9ea283857b7a22487a63fd1b3dfd8415be0-image.png)

<br />

4. Name the model and click "Next" to proceed.

## Schema Mapping

Map the schema by associating your input data with Lifesight's data types. 

1. Select the column containing the date.
2. Select the column containing the KPI you want to measure and map it to the metric intended to serve as your business outcome data (KPI). 
3. Define the marketing spend and contextual variables. You can also add impressions and clicks from paid and organic campaigns.
4. Map the nature of each input from the drop-down i.e Discrete, Continuous, Binary, Categorical Ordinal and Categorical Nominal.
5. Click on `Next` to proceed.

![](https://files.readme.io/914b64c9caf90f9fed0df46831ffb01086ed2ad002c0e9d2105e264931a00524-image.png)

<br />

## Relationship Mapping

On this page, all plausible relationships between the variables selected on the features page are displayed, except the date section. This capability enables you to refine the model by concentrating on the causal links that are most pertinent to their investigation. The relationships are categorized into two types:

* **Potential Relationships:** These denote possible causal relations that might exist between two variables.
* **Forbidden Relationships:** These are relationships that have been explicitly identified by the user as lacking a causal nature.

Lifesight automatically detects and selects all plausible relationships between the variables chosen on the features page. Users can review and adjust these selections if needed

Mark the relationships and click `Create Model` to proceed.

The model will start running, and the status on the Causal Inference page will be either started or pending. Once status becomes success, you can view the Insights tab.
