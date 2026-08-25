---
title: '[4.0][WIP] MMM Calibration'
excerpt: Review and manage calibration evidence for Marketing Mix Modeling.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# MMM Calibration

Calibration helps align channel estimates with trusted incrementality evidence. It adds external evidence to the model without replacing the observed marketing, KPI, and contextual data used for estimation.

[IMAGE PLACEHOLDER: Calibration summary for a model]

## What to review

For each calibration entry, confirm:

- Channel or tactic
- Calibration start and end dates
- Average iROAS
- Confidence level
- Calibration type
- Evidence source
- Last updated date

The evidence should be relevant to the same KPI, market, channel definition, and business context as the model.

## Add or update calibration

Calibration can be added during model creation or from the **Calibrate** action on an eligible successful model. You can also review and change calibration inputs while retraining a model.

[VIDEO PLACEHOLDER: Reviewing and editing channel calibration inputs]

Use confidence to reflect the reliability of the evidence. Strong experimental evidence can support a higher confidence value. Directional or less comparable evidence should use a lower value or be excluded.

## Review the calibrated model

After processing completes, review calibration information with the model diagnostics and channel results. Check:

- Overall model health and fit
- Paid media contribution
- Channel iROAS and uncertainty
- Consistency with the calibration evidence
- Material changes from the previous model version

[IMAGE PLACEHOLDER: Model diagnostics and calibrated channel results]

Calibration and refresh serve different purposes. Calibration introduces trusted incrementality evidence. Refresh extends an existing model with newer observations. Retraining creates a new model version when configuration or evidence needs to change more broadly.

> Calibration should support the model with credible evidence, not force a predetermined channel result.
