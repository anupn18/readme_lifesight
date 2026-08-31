---
title: '[4.0][WIP] Marketing Mix Modelling (Main Page)'
excerpt: Understand the Marketing Mix Modeling workflow in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Causal Marketing Mix Modelling in Lifesight explains how paid media, organic activity, contextual factors, halo effects, and baseline demand contribute to a business outcome.

Unlike attribution, which begins with individual customer touchpoints, MMM uses aggregated time-series data. This makes it suitable for measuring channels where user-level paths are incomplete or unavailable.

**[IMAGE PLACEHOLDER: Marketing Mix Modelling workflow in Lifesight 4.0]**

## How the workflow fits together

1. Prepare the model data and create a model schema.
2. Create a model and define its variables, configuration, calibration evidence, and causal relationships.
3. Review the model in the Models workspace.
4. Promote a model only after its data, diagnostics, causal structure, and contribution results are suitable for decision-making.
5. Use the promoted model in Planner, or refresh and retrain it as new evidence becomes available.

## Review a model

The Models workspace organizes model output into tabs. Some tabs are hidden by default and can be enabled from **Customize Tabs**.

* **Data:** Validate coverage, trends, model inputs, and correlations.
* **Diagnostics:** Review fit, backtesting, residuals, channel transformations, decomposition, and calibration evidence.
* **Graph:** Inspect the model's causal structure and direct, indirect, and total effects.
* **Contribution:** Understand incremental outcome, efficiency, contribution share, uncertainty, and response curves.
* **Creatives:** Review modelled creative interactions, quality, and positive or negative impact.
* **Interaction:** Identify synergy, cannibalization, and neutral relationships between media variables.
* **Insights:** Explore media and baseline analyses using ranked, time-based, and decomposition views.
* **Refresh:** Review refresh history after a model has been refreshed.

> 📘 Review the model as a complete system. A strong accuracy score does not replace backtesting, plausible causal relationships, stable channel behavior, or appropriate business context.

## Model lifecycle

Models move through training, review, promotion, refresh, and retraining workflows. Models that are still processing or have failed expose only the tabs with available results. Review access can also depend on status and permissions.

Use refresh when new periods follow the existing schema and model structure. Use retraining when the variables, causal assumptions, calibration evidence, or configuration need to change.

**[VIDEO PLACEHOLDER: From model creation to model review and planning]**

## Recommended reading

Start with **Setting up your Mix Model**, then use **Model Overview** to navigate the Models workspace. The tab-specific pages explain what each result means and how to use it.
