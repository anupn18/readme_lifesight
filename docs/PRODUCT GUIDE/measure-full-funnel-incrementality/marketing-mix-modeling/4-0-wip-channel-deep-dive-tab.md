---
title: '[4.0][WIP] Contribution'
excerpt: Review channel contribution, efficiency, response, and uncertainty.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The **Contribution** tab explains how the selected model distributes the outcome across paid media, baseline, contextual, halo, organic, and unknown groups.

**[IMAGE PLACEHOLDER: Contribution tab with grouped channel and tactic rows]**

## Read the contribution table

Expand a channel to review its tactics. Available columns depend on the model outcome and cost configuration. They can include:

* Spend
* Incremental outcome and incremental efficiency
* Contribution percentage
* Confidence interval
* Marginal efficiency
* Incremental profit and profit efficiency
* Causal status

Incremental efficiency uses the modelled incremental outcome. It should not be compared directly with platform-reported efficiency without accounting for the different measurement methods.

## Interpret contribution and efficiency together

Contribution shows how much of the outcome is assigned to a driver. Efficiency shows the incremental outcome generated per unit of spend, or the spend required per incremental outcome.

A high-contribution channel is not always the best place for additional spend. Review marginal efficiency and the response curve to understand what the next unit of investment may produce.

## Review uncertainty

Use the confidence interval to understand the range around an estimate. Wide intervals indicate greater uncertainty. Use causal status, Graph, Diagnostics, and experiment evidence to decide how much confidence to place in the result.

The **Unknown** group can appear when a partial refresh leaves some contribution unmatched. It is not a causal-status label.

## Compare periods

When comparison is enabled, review spend, incremental outcome, and efficiency together. A contribution increase may be caused by more investment, a change in efficiency, or a different overall outcome mix.

## Response curves

Response curves show fitted outcome across spend levels. Use them to identify diminishing returns and compare current efficiency with marginal efficiency.

> 📘 The response-curve Period selector is independent of the page date range. It controls the curve calculation and marginal-efficiency fields.

Immediate and carryover effects are reviewed in Diagnostics.

**[VIDEO PLACEHOLDER: Reading contribution, uncertainty, and response curves]**
