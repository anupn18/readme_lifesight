---
title: '[4.0][WIP] Model Retraining'
excerpt: Create a new model version with updated configuration and calibration.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Model Retraining

Retraining lets you create a new version of a successful model using updated configuration and calibration settings. The original model remains unchanged, so you can compare the retrained model before deciding which version to use.

[IMAGE PLACEHOLDER: Model list with the Retrain action highlighted]

## Before you begin

You can retrain a model when its status is **Success** or **Refresh Success**. Review the existing model results and prepare any changes to the model window, variables, calibration inputs, or advanced settings.

## Retrain a model

1. Go to **Measure > Marketing Mix Modeling**.
2. Open the model you want to retrain.
3. Select **Retrain**.

The retraining flow displays the active KPI, data source, country, currency, and variables from the source model. Source details and variables are read-only in this flow.

[VIDEO PLACEHOLDER: Starting a retraining flow from a successful model]

## Review calibration

Existing calibration inputs are inherited where applicable. You can add, edit, or remove calibration entries before submitting the retraining job.

For each calibration entry, review the channel, calibration window, average iROAS, confidence, calibration type, and source.

[IMAGE PLACEHOLDER: Calibration step in the retraining flow]

## Configure the retrained model

Enter a unique model name and review the model configuration:

- Model start and end dates
- Time aggregation
- Refresh frequency
- Training and validation split
- Contextual variables
- Advanced model settings

Adjust only the settings needed for the new model version. The original model configuration remains available for reference.

[IMAGE PLACEHOLDER: Model configuration for a retraining job]

## Submit and compare

Submit the retraining job after reviewing the configuration. Lifesight creates a new model and keeps the source model unchanged. Once processing is complete, compare model health, fit, contribution, calibration, and business insights across the two versions.

[IMAGE PLACEHOLDER: Original and retrained models shown in the model list]

> Retraining creates a separate model. It does not overwrite the model used to start the flow.
