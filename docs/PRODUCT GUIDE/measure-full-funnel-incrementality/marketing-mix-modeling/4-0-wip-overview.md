---
title: '[4.0][WIP] Model Overview'
excerpt: Review model health, performance, contribution, and insights in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The Models workspace is where you review trained models, compare their results, and manage their lifecycle.

**[IMAGE PLACEHOLDER: Models workspace with model selector, date range, and tabs]**

## Select a model

Use the model selector to choose an available promoted model for the active workspace and outcome. Open **Model List** to review other trained, challenger, in-progress, failed, archived, or merged models.

The tabs that are available depend on model status and output. In-progress and failed models expose only the results that can be loaded. Merged models do not include every output produced by a fully trained model.

## Set the analysis period

Use the page date range for date-scoped analysis in tabs such as Data, Contribution, Insights, and Interaction. When a comparison is available, review changes in spend, outcome, and efficiency together.

> 📘 The Period selector in the response-curve section is separate from the page date range. It controls the curve calculation and marginal efficiency values.

## Customize the workspace

Use **Customize Tabs** to show or hide optional tabs. Creatives, Interaction, and Insights are hidden by default. A tab may also be unavailable when the selected model does not contain the required output.

## Recommended review order

1. Open **Data** and confirm that the input period, trends, and variables are plausible.
2. Open **Diagnostics** and review model fit, backtesting, residuals, transformations, and decomposition.
3. Open **Graph** and confirm that the causal structure matches business knowledge.
4. Open **Contribution** and assess incremental outcome, efficiency, uncertainty, and response curves.
5. Enable **Creatives**, **Interaction**, and **Insights** when those outputs are relevant.
6. Promote or use a model for planning only after the full review is complete.

## Manage models

Model List shows model name, outcome, status, type, granularity, accuracy, creation date, and model end date. Depending on status and permissions, available actions can include:

* View the model schema
* Refresh or retrain the model
* Promote a successful challenger
* Create a plan from a promoted model
* Merge compatible models
* Archive, restore, or delete a model

Calibration inputs are configured during model creation or retraining. The Diagnostics tab displays the calibration evidence used by the selected model.

**[VIDEO PLACEHOLDER: Navigating Model List and the Models workspace]**
