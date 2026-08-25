---
title: '[4.0][WIP] Marketing Mix Modelling (Main Page)'
excerpt: Understand the Marketing Mix Modeling workflow in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Causal MMM is the foundation of Unified Marketing Measurement in Lifesight. It provides a top-down view of how paid media, organic activity, contextual factors, and baseline demand work together to drive a business outcome.

<Callout icon="ℹ️" theme="info">
  **What is a top-down approach?**

  Unlike attribution methods that begin with individual customer touchpoints, MMM begins with an aggregate outcome, such as weekly revenue or orders, and estimates how much each business driver contributed to it.
</Callout>

## Lifesight's Causal Mix Modelling Approach

Lifesight 4.0 combines structured causal assumptions, model validation, contribution analysis, and experiment calibration in one model workspace.

**[IMAGE PLACEHOLDER: Lifesight 4.0 MMM workflow from data to decisions]**

### Pillar 1: Structured Causal Modelling

During model creation, you map paid media, organic, contextual, halo, and outcome variables. You then review the causal graph and mark each possible relationship as **Potential** or **Forbidden**.

The trained model exposes its causal structure in the **Graph** tab. Select a node to review incoming and outgoing relationships, including direct, indirect, and total effects.

### Pillar 2: Model Validation

The **Diagnostics** tab evaluates whether a model is suitable for decision-making. It includes:

* Model fit health and pass, warn, or fail checks
* Actual versus predicted outcome
* Training and validation periods
* Backtest accuracy and holdout error
* Residual analysis
* Saturation, adstock, and time-to-conversion curves
* Time-series decomposition

> 📘 A model should be reviewed as a complete system. Strong in-sample accuracy alone is not enough. Holdout performance, stability, residuals, and causal evidence should also support the result.

### Pillar 3: Incrementality Calibration

Where experiment evidence is available, paid channels can be calibrated using incremental ROAS, confidence, and an experiment date range. Calibration can be added while creating a model, inherited from an eligible model, or managed for an existing successful model.

Calibration connects model estimates with observed lift and improves confidence in channel-level decisions.

### Pillar 4: Contribution and Decision Support

The **Contribution** tab shows how the selected model distributes the outcome across paid, baseline, contextual, halo, organic, and unknown groups. It also provides channel and tactic metrics, confidence intervals, causal evidence, immediate and carryover effects, and saturation curves.

Use the **Planner** to turn a successful model into budget scenarios. Planner compares current and optimized allocations, applies channel constraints, forecasts the selected outcome, and supports scenario comparison before a decision is promoted.

**[VIDEO PLACEHOLDER: From a trained Mix Model to a budget decision in Lifesight 4.0]**

## Key Benefits for Your Business

* **Understand incremental impact:** Separate modelled contribution from platform-reported outcomes.
* **Evaluate confidence:** Review diagnostics, causal evidence, and confidence intervals before acting.
* **Plan across channels:** Test budget scenarios using response curves and business constraints.
* **Incorporate experiments:** Anchor channel estimates to observed incrementality where evidence is available.
* **Keep decisions current:** Refresh or retrain models as new data and market conditions emerge.

> 👍 Start with well-prepared data, review model health before promotion, and use calibration and refresh workflows to keep the model aligned with the business.
