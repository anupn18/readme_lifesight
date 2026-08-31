---
title: '[4.0][WIP] Model Retraining'
excerpt: Create a new model version with updated configuration and calibration.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Retraining creates a new model from an existing model while allowing selected configuration and calibration inputs to be updated.

## When to retrain

Retrain when you need to change calibration evidence, configuration, or assumptions, or when refresh is no longer appropriate for the business structure.

## Start retraining

1. Open **Model List**.
2. Open the action menu for an eligible model.
3. Select **Retrain**.
4. Enter a unique name for the new model.
5. Review the inherited setup and update the editable steps.
6. Submit the model for training.

**[IMAGE PLACEHOLDER: Retraining workflow with inherited and editable fields]**

The data source and variable selection are inherited and read-only in retraining. Model configuration and calibration evidence can be updated. Review the complete setup before submission so the new result can be compared with the source model.

## Review the retrained model

Treat the result as a new challenger. Review Data, Diagnostics, Graph, and Contribution before promotion. Compare backtest performance, contribution shifts, uncertainty, and channel behavior with the current promoted model.

Use a name that identifies the reason or period for retraining. This makes model comparisons and lifecycle management easier.

**[VIDEO PLACEHOLDER: Retraining a model and comparing it with the source model]**
