---
title: '[4.0][WIP] Causal flags'
excerpt: Use causal graph relationships to understand modeled effects.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Causal flags help you judge whether a channel-level estimate is suitable for decision-making. Lifesight 4.0 presents this evidence in the **Contribution** table and provides the underlying relationship paths in the **Graph** tab.

## Understanding Causality in MMM

Marketing channels often move together. A model must separate each channel's effect from other media, baseline demand, seasonality, promotions, and external events. When that separation is weak, the channel estimate requires additional review.

**[IMAGE PLACEHOLDER: Causal indicator in the Lifesight 4.0 Contribution table]**

## Causal Evidence States

### Confident

The model has stronger evidence that the channel or tactic contributes incrementally to the outcome.

Use the estimate with:

* Its confidence interval
* Incremental efficiency such as iROAS or iCPA
* Immediate and carryover effects
* The selected saturation-curve period
* Overall model diagnostic health

### Watch

The estimate needs investigation before it supports a major decision. Common causes include limited spend variation, correlated media activity, a short data window, a missing control variable, or coefficient instability.

Review the Data, Diagnostics, and Graph tabs. If the channel is strategically important, consider adding experiment evidence through calibration.

### Unknown

The model does not have enough usable information to classify the selected result. This can occur when a model result is incomplete, a partial refresh leaves unattributed contribution, or the selected row does not carry a causal classification.

## Using the Graph Tab

Select a node in the causal graph to inspect incoming and outgoing effects. Lifesight separates direct effects from indirect effects that flow through another variable.

> 📘 A causal flag summarizes evidence for a row. The graph explains the paths that contribute to that result.

## Recommended Actions

| Observation | What to check |
| :--- | :--- |
| A channel is marked Watch | Correlation, spend variation, confidence range, and coefficient stability |
| Two channels have similar movement | Raw and transformed correlation matrices and input granularity |
| The graph contains an implausible path | Causal relationship settings used when the model was created |
| Model fit is weak | Diagnostics failures, residuals, missing controls, and training window |
| Experiment evidence disagrees | Experiment quality, date alignment, iROAS input, and calibration confidence |

**[VIDEO PLACEHOLDER: How to interpret causal evidence in Lifesight 4.0]**
