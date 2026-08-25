---
title: '[4.0][WIP] Model Overview'
excerpt: Review model health, performance, contribution, and insights in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The Lifesight 4.0 model workspace brings model data, health, causal structure, contribution, and insights into a set of focused tabs. Use the model selector at the top of the page to choose the model you want to review.

**[IMAGE PLACEHOLDER: Lifesight 4.0 model workspace with the model selector and tab bar]**

## Select a Model

The model selector lists promoted models for the active workspace and outcome. To review any trained, in-progress, archived, or challenger model, open **Model List**.

The summary strip shows the selected model and its current status. Available tabs depend on the model status. Models that are still training or have failed expose only the data and graph surfaces that can be loaded safely.

## Date Range

Use the date-range control to select the period you want to analyze. The selected range is shared by date-scoped model tabs, including Data, Contribution, Insights, and Interaction.

> 📘 The Period selector inside Saturation Curves is independent of the page date range. It controls the response-curve calculation and marginal efficiency fields only.

## Data Tab

The **Data** tab provides a preliminary review of the information used by the model.

### Metrics Summary

Review the number of spend and control variables, total spend, total outcome, blended efficiency, and data quality for the selected period.

### Time Series Trends

Select one or more outcome, spend, paid, organic, or control variables to plot over time. You can compare against a prior period, prior year, prior quarter, or another supported comparison window.

### Model Input

Use the input table to inspect variable category, spend, mean, observations, aggregation, and available media metrics. Search, filter, and sort the table to locate a specific field.

### Correlation Matrix

Switch between **Raw Input** and **Transformed** correlations where transformed results are available. Select a heatmap cell to inspect the relationship between two variables in a scatter plot.

**[IMAGE PLACEHOLDER: Data tab showing the KPI strip, time-series chart, input table, and correlation matrix]**

## Model List and Lifecycle

Open **Model List** to review model name, outcome, status, type, granularity, accuracy, creation date, and model end date. From this view, eligible users can:

* Open or promote a successful challenger model
* Refresh or retrain an eligible model
* Calibrate a successful model
* Merge compatible models
* Archive, restore, or delete a model where permitted

## Continue Your Analysis

After validating the input data, continue to:

* **Diagnostics** for model fit and validation checks
* **Graph** for causal structure and effect paths
* **Contribution** for channel and tactic contribution
* **Insights** for media, baseline, trend, and seasonality analyses
* **Interaction** for channel synergy and cannibalization

**[VIDEO PLACEHOLDER: Navigating the Lifesight 4.0 model workspace]**
