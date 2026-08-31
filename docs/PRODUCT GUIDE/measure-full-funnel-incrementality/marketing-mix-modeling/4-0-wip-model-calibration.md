---
title: '[4.0][WIP] Model Calibration'
excerpt: Add incrementality evidence during model creation or calibration.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Calibration uses experiment evidence to guide a paid-media estimate during model training.

## When calibration is useful

Use calibration when a reliable incrementality experiment covers a channel and period represented in the model data. The evidence should use a comparable outcome and a clearly defined experiment window.

## Add calibration evidence

Calibration is configured in the **Calibration** step while creating a model or retraining an existing model.

1. Select **Add calibration**.
2. Choose the paid-media variable.
3. Enter the experiment start and end dates.
4. Enter the incremental ROAS or supported incremental efficiency value.
5. Enter the confidence value.
6. Review the entries before submitting the model.

Eligible calibration values can also be inherited from the champion model during creation or retraining.

> 📘 Experiment results are entered manually. Directly adding an experiment from the experiment picker is not currently available.

**[IMAGE PLACEHOLDER: Calibration step with channel, date range, incremental efficiency, and confidence]**

## Review calibration

After training, open **Diagnostics** and review the calibration summary. Confirm that the channel, dates, incremental efficiency, and confidence match the evidence used for training.

Calibration should be interpreted with the model's backtesting, uncertainty, causal structure, and contribution results. It strengthens the connection to observed lift, but does not replace model validation.

## Update calibration evidence

To change calibration inputs for an existing model, start a retraining workflow and edit the Calibration step. The existing model's Diagnostics tab is read-only.

**[VIDEO PLACEHOLDER: Adding calibration during model creation or retraining]**
