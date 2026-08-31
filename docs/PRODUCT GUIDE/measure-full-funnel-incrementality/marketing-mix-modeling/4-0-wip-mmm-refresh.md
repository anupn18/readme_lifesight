---
title: '[4.0][WIP] Model Refresh'
excerpt: Refresh a successful model with newly available observations.
deprecated: false
hidden: true
metadata:
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

**[IMAGE PLACEHOLDER: Model List action menu and refresh dialog]**

## Use the Refresh tab

The **Refresh** tab becomes available after a refresh result exists. It is shown for models with **Refresh Success** or **Refresh Failed** status. Use it to review refresh history and start a subsequent refresh.

Review the refresh window, status, changes in available variables, and comparison output. After a successful refresh, check Contribution and Diagnostics before using the updated result.

## Partial and unmatched contribution

If a refresh cannot match every contribution component, the unmatched amount can appear in the **Unknown** group in Contribution. Investigate schema, taxonomy, and variable changes before relying on the refreshed result.

## Troubleshoot a failed refresh

Check that the new file uses the original schema and aggregation, has a continuous date range, and contains the required variables. If the business structure has changed, use retraining instead of repeatedly refreshing the old structure.

**[VIDEO PLACEHOLDER: Running the first refresh and reviewing refresh history]**
