---
title: '[4.0][WIP] Causal Flags'
excerpt: Interpret causal evidence and confidence signals in Marketing Mix Modeling.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Causal evidence indicates how confidently a model can separate a channel's incremental effect from correlated activity and other business drivers. In Lifesight 4.0, causal evidence is reviewed in the **Contribution** and **Graph** tabs.

## Why Causal Evidence Matters

A channel can have a strong modelled contribution without having equally strong causal evidence. Use causal status together with confidence intervals, diagnostic health, experiment evidence, and business context before reallocating budget.

> ℹ️ Causal evidence is a decision aid. It does not replace model review or experiment validation.

## Causal Status in the Contribution Tab

The Contribution table shows a causal indicator for eligible channel and tactic rows.

| Status | Meaning | Recommended action |
| :--- | :--- | :--- |
| **Confident** | The model has stronger evidence that the variable contributes incrementally to the outcome. | Use the estimate with its confidence interval and response curve when planning. |
| **Watch** | The relationship has weaker or less stable evidence. | Investigate data variation, correlation, diagnostics, and available experiments before making a large change. |
| **Unknown** | The model cannot provide a usable classification for the selected row or period. | Confirm model status, refresh completeness, and variable coverage. |

**[IMAGE PLACEHOLDER: Contribution table showing causal evidence and confidence intervals]**

## Investigating a Causal Result

### Review the Graph

Open the **Graph** tab and select the variable. Review:

* Incoming and outgoing relationships
* Direct, indirect, and total effects
* Positive and negative paths
* Contribution over the selected period

The width of an edge represents the relative magnitude of the effect. Use the node detail panel to distinguish a direct relationship from impact that travels through an intermediate variable.

### Review Correlation

Open the **Data** tab and inspect the raw and transformed correlation matrices. High correlation between media variables can make their individual effects harder to separate.

### Review Diagnostics

Check holdout performance, residuals, stability, and model fit. A channel estimate should not be treated as reliable when the overall model has unresolved failures.

### Review Calibration

Where a completed lift study or geo experiment exists, calibrate the paid channel using incremental ROAS and confidence. Calibration provides an external anchor for the model estimate.

## Improving Causal Evidence

* Include all material marketing and business drivers.
* Avoid combining unrelated activities in one input field.
* Maintain sufficient history and spend variation.
* Separate highly correlated tactics where the data supports it.
* Add relevant promotions, holidays, pricing, and competitor variables.
* Run controlled experiments for channels with high spend and weak evidence.
* Refresh or retrain the model when relationships have materially changed.

**[VIDEO PLACEHOLDER: Investigating causal evidence across Contribution, Graph, Data, and Diagnostics]**
