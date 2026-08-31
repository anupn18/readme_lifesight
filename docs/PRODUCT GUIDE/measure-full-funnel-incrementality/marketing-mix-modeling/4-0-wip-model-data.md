---
title: '[4.0][WIP] Data'
excerpt: Understand the attributes and configuration of a Marketing Mix Model.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The **Data** tab helps you validate the information used by the selected model before interpreting its results.

**[IMAGE PLACEHOLDER: Data tab with summary metrics, trends, inputs, and correlations]**

## Summary metrics

The summary shows the selected period's spend and control-variable counts, total spend, total outcome, blended efficiency, and data-quality information.

Use these metrics as a first check. Unexpected totals, missing variables, or a date range that does not match the intended analysis period should be investigated before continuing.

## Time-series trends

Plot outcome, spend, paid, organic, or control variables to understand how they move over time. Select multiple variables when you need to compare timing or scale, and use the available comparison period to add context.

Look for:

* Missing or flat periods
* Sudden changes that may reflect tracking or taxonomy updates
* Spend activity outside the expected campaign window
* Outcome changes that coincide with known promotions or business events

Similar movement between two variables can be useful context, but correlation alone does not establish causality.

## Model inputs

The input tables describe the variables available to the model. Search, filter, and sort to review category, spend, mean, observations, aggregation, and available media metrics.

Confirm that variables are classified correctly. Paid, organic, contextual, halo, and outcome variables play different roles in the model and in downstream contribution reporting.

## Correlation matrix

Switch between **Raw Input** and **Transformed** correlations where transformed results are available. Select a heatmap cell to inspect the relationship in a scatter plot.

High correlation between paid variables can make their individual effects harder to separate. High correlation between a media variable and the outcome may be expected, but should still be reviewed with Diagnostics and Graph.

## Before you continue

Continue to Diagnostics when the selected period, totals, variable classifications, and time-series patterns are consistent with the source data and business context.

**[VIDEO PLACEHOLDER: Reviewing model data and correlations]**
