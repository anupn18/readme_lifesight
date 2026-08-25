---
title: '[4.0][WIP] Channel Deep Dive'
excerpt: Review channel contribution, efficiency, response, and uncertainty.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Lifesight 4.0 provides channel and tactic analysis in the **Contribution** tab. Expand a channel to review its tactics, then use the drill-down and response-curve views to understand performance in the selected period.

### Accessing Channel Analysis

1. Navigate to **Measure > Models**.
2. Select the promoted model and outcome.
3. Open the **Contribution** tab.
4. Set the page date range.
5. Search for a channel or tactic, then expand the relevant row.

**[IMAGE PLACEHOLDER: Contribution table with one channel expanded to show tactics]**

## Key Metrics

Available metrics depend on the model KPI and model type. They can include:

* **Spend:** Media investment during the selected period.
* **Incremental Outcome:** Modelled revenue, orders, conversions, or another KPI generated incrementally.
* **iROAS:** Incremental revenue or profit per unit of spend.
* **iCPA:** Spend per incremental order or conversion.
* **Contribution Share:** The channel or tactic's share of total modelled contribution.
* **Confidence Interval:** The lower and upper range around the estimate.
* **Causal Evidence:** Whether the result is classified as confident, watch, or unknown.
* **Immediate and Carryover Effect:** The split between same-period response and response that persists into later periods.
* **Profit Metrics:** Incremental profit, margin, and iPOAS when applicable.

## Compare Date Ranges

Use the page-level comparison controls to compare the selected range with another period. Review changes in spend, incremental outcome, and efficiency together. A higher contribution can be caused by more investment, stronger efficiency, or both.

## Saturation Curves

The Saturation Curves section shows fitted channel response across different spend levels.

> 📘 The curve Period selector is separate from the page date range. It controls curve generation and marginal efficiency values.

Use the curves to review:

* Current spend relative to the fitted response curve
* Where diminishing returns begin
* Marginal incremental efficiency
* How the response changes when the applied period changes

**[IMAGE PLACEHOLDER: Channel saturation curve with current-spend reference line]**

## Investigating a Channel

When a channel requires deeper review:

1. Check its confidence interval and causal evidence.
2. Open **Graph** and inspect direct and indirect effect paths.
3. Open **Diagnostics** and review the channel's adstock and saturation assumptions.
4. Open **Data** and inspect time-series movement and correlation.
5. Open **Interaction** to check synergy or cannibalization with other channels.
6. Use Planner to simulate an allocation change.

**[VIDEO PLACEHOLDER: Performing a channel deep dive in Lifesight 4.0]**
