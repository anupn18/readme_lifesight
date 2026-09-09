---
title: '[4.0][WIP] Model Refresh: Refresh your marketing model with the latest data'
excerpt: Refresh a successful model with newly available observations.
deprecated: false
hidden: true
metadata:
  title: 'Model Refresh: Refresh your marketing model with the latest data'
  keywords:
    - Lifesight Model Refresh
  robots: noindex
---
A model refresh incorporates new periods of data while retaining the current model structure. Use it when the schema and underlying business relationships remain suitable.

## Choose refresh or retraining

Refresh when new data follows the existing schema and you want to extend the model results. Retrain when variables, relationships, calibration evidence, configuration, or market behavior require a deeper change.

## Run the first refresh

The first refresh is started from the eligible model's action menu in **Model List**. Models with **Success**, **Refresh Success**, or **Refresh Failed** status can be eligible.

1. Open **Model List**.
2. Open the action menu for the model.
3. Select the refresh action.
4. Upload and review the updated data.
5. Submit the refresh.

<br />

![](https://files.readme.io/97d3074aeeb45ede9f9125309f44df864bc006f65bcb58b9cd43cefa130129ed-Screenshot_2026-09-09_at_4.03.25_PM.png)

<br />

![](https://files.readme.io/0ad8a98fd62fabe9584e0f2f7f54574f3c2d960bfc7e8e474bb7f53ca6c61491-Screenshot_2026-09-09_at_4.02.53_PM.png)

## Use the Refresh tab

The **Refresh** tab becomes available after a refresh result exists. It is shown for models with **Refresh Success** or **Refresh Failed** status. Use it to review refresh history and start a subsequent refresh.

Review the refresh window, status, changes in available variables, and comparison output. After a successful refresh, check Contribution and Diagnostics before using the updated result.

## Partial and unmatched contribution

If a refresh cannot match every contribution component, the unmatched amount can appear in the **Unknown** group in Contribution. Investigate schema, taxonomy, and variable changes before relying on the refreshed result.

## Troubleshoot a failed refresh

Check that the new file uses the original schema and aggregation, has a continuous date range, and contains the required variables. If the business structure has changed, use retraining instead of repeatedly refreshing the old structure.

**\[VIDEO PLACEHOLDER: Running the first refresh and reviewing refresh history]**
