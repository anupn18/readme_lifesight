---
title: '[4.0][WIP] Model Calibration'
excerpt: Add incrementality evidence during model creation or calibration.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Model Calibration

Model calibration incorporates trusted experimental evidence into model estimation. Use calibration when you have incrementality results or other reliable evidence for a paid media channel or tactic.

[IMAGE PLACEHOLDER: Calibration step in the model creation flow]

## Add calibration during model creation

In the **Calibration** step of the model creation flow, select **Add calibration** and provide:

- Paid media channel or tactic
- Calibration start and end dates
- Average or incremental iROAS
- Confidence level

The calibration window must fall within the model date range. Lifesight assigns the appropriate calibration treatment based on the evidence and selected period.

[VIDEO PLACEHOLDER: Adding a calibration entry while creating a model]

If eligible calibration evidence is available, you can inherit it and review the values before continuing. Remove any inherited entry that should not be applied to the new model.

## Calibrate an existing model

For a successful model, select **Calibrate** from the model actions. The calibration dialog lets you add, edit, and remove channel-level calibration entries.

Review the following fields for each entry:

- Average iROAS
- Confidence
- Calibration window
- Calibration type
- Source
- Last updated date

[IMAGE PLACEHOLDER: Calibration dialog for an existing model]

## Calibration guidance

Use evidence that is comparable to the market, channel definition, KPI, and time period represented by the model. Higher confidence should be reserved for evidence with a strong experimental design and reliable measurement.

Avoid adding multiple calibration entries that describe the same channel and period unless they represent distinct, valid evidence.

## Review calibration results

After calibration is processed, review the model diagnostics and channel results. Check model health, fit, contribution, and whether calibrated channel estimates remain consistent with the underlying evidence.

[IMAGE PLACEHOLDER: Calibration information shown with model diagnostics]
