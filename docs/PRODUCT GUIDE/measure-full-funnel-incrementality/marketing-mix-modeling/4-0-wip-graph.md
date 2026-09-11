---
title: '[4.0][Updated] Causal Graph: See how your channels work together'
excerpt: Use causal graph relationships to understand modeled effects.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The Causal Graph tab shows the causal structure used by the selected model.

A model does not just estimate how much each channel contributed. It works from a view of how your drivers relate to each other: which ones influence outcomes directly, and which ones work by shifting something else first. Upper-funnel video that lifts branded search is the classic case.&#x20;

The spend shows up in one place and part of its value shows up in another.

This graph makes that view visible. You can see every relationship the model is using, trace how one driver reaches your outcome, and check whether the structure matches what you know about the business.&#x20;

When a channel's contribution looks lower than expected, this is usually where the explanation is.

![](https://files.readme.io/893a71b3d909984a66767fe8571f8569ea2d02a960b964bf03f88caf7153c7e7-Screenshot_2026-09-11_at_12.37.11_PM.png)

## Explore the graph

The graph lays your model out in three columns:

-Inputs are the variables you control or account for, including media channels, control variables, and CRM or owned activity.&#x20;

-Intermediates are the variables that sit in between, like demand generation and demand capture.&#x20;

-Outcomes are what you are measuring, such as revenue.

The lines between them show the relationships the model is using, coloured by whether the effect is positive or negative. Hover over a variable to highlight the effects running into and out of it.

Click a variable to open its detail panel, which shows:

- Total inflow, the combined effect of everything upstream that feeds into it
- Total outflow, the combined effect it passes on to downstream variables
- Direct, indirect, and total effect on the outcome, where available
- Contribution over time and the period total for the selected date range

Inputs usually show no inflow, since nothing in the model feeds them. Outcomes usually show no outflow, since nothing sits downstream of them.

## Trace the effect paths before comparing numbers

- Direct effect is the effect a variable has on the outcome with nothing in between. The line runs straight from the variable to the outcome.
- Indirect effect is the effect that travels through one or more intermediates. The variable moves an intermediate such as demand generation, and that intermediate is what moves the outcome.
- Total effect combines the direct and indirect paths that are available. This is the incremental revenue the model attributes to the variable across every route it takes.

## Causal evidence in Contribution

Contribution can display a causal status for a channel or tactic. **Confident** indicates stronger causal support. **Watch** indicates lower confidence and requires additional review. A dash indicates that no causal status is available.

Use Graph to inspect the relevant paths, then check uncertainty and model behaviour before acting on the estimate.

**\[VIDEO PLACEHOLDER: Selecting a node and tracing direct and indirect effects]**
