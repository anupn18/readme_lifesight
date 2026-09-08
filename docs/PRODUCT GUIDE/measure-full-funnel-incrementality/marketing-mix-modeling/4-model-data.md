---
title: '[4.0][Updated] Model Data'
excerpt: See what your model is built on, so you can trust what it tells you.
deprecated: false
hidden: true
metadata:
  title: Data
  keywords:
    - Lifesight Model Data
  robots: noindex
---
The **Data** tab helps you validate the information used by the selected model before interpreting its results.

![](https://files.readme.io/a125f995035b95515d03f2c0e2734f43a1c681e9015c86dc0162e66c2dd90057-Screenshot_2026-09-08_at_11.13.11_AM.png)

## Summary metrics

The summary shows the selected period's spend and control-variable counts, total spend, total outcome, blended efficiency, and data-quality information.

Use these metrics as a first check. Unexpected totals, missing variables, or a date range that does not match the intended analysis period should be investigated before continuing.

## Time-series trends

Plotting outcome, spend, paid, organic, and control variables over time shows you how each one behaves and where they move together. Multiple variables can be plotted at once when timing or scale needs comparing, and the comparison period adds context.

A few things worth catching here:

- Gaps or flat stretches where data may be missing
- Sharp shifts that usually trace back to tracking or taxonomy changes
- Spend showing up outside the campaign window it belongs to
- Outcome movements that line up with promotions or known business events

Similar movement between two variables can be useful context, but correlation alone does not establish causality.

## Model inputs

The input tables describe the variables available to the model. Search, filter, and sort to review category, spend, mean, observations, aggregation, and available media metrics.

Confirm that variables are classified correctly. Paid, organic, contextual, halo, and outcome variables play different roles in the model and in downstream contribution reporting.

## Correlation matrix

Switch between **Raw Input** and **Transformed** correlations where transformed results are available. Select a heatmap cell to inspect the relationship in a scatter plot.

![](https://files.readme.io/ebe75bb2083610d09ada1397b65bab8ad7476a7d7e6432e306239b501524a1cb-Screenshot_2026-09-08_at_11.14.30_AM.png)

High correlation between paid variables can make their individual effects harder to separate. High correlation between a media variable and the outcome may be expected, but should still be reviewed with Diagnostics and Graph.

## Before you continue

Continue to Diagnostics when the selected period, totals, variable classifications, and time-series patterns are consistent with the source data and business context.

**\[VIDEO PLACEHOLDER: Reviewing model data and correlations]**
