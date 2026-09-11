---
title: '[4.0][Updated] Causal Graph: See how your channels work together'
excerpt: Use causal graph relationships to understand modeled effects.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The Causal Graph tab shows the causal structure used by the selected model.

A model does not just estimate how much each channel contributed. It works from a view of how your drivers relate to each other: which ones influence outcomes directly, and which ones work by shifting something else first. Upper-funnel video that lifts branded search is the classic case. The spend shows up in one place and part of its value shows up in another.

This graph makes that view visible. You can see every relationship the model is using, trace how one driver reaches your outcome, and check whether the structure matches what you know about the business.&#x20;

When a channel's contribution looks lower than expected, this is usually where the explanation is.

![](https://files.readme.io/4c1895cdbcce76925701f4e46ba879e35668e0f4781016b9479c12f2ca4c3b00-Screenshot_2026-09-11_at_12.26.25_PM.png)

## Explore the graph

Each node represents a model variable. Connections show the relationships included in the causal structure.

Select a node to review:

* Incoming relationships that may affect the selected variable
* Outgoing relationships through which the variable may affect others
* Direct, indirect, and total effects where they are available

## Understand effect paths

* **Direct effect** is the relationship between two connected variables without an intermediate node.
* **Indirect effect** passes through one or more other variables.
* **Total effect** combines the available direct and indirect paths.

A channel can have a modest direct effect and still have a material total effect when it influences another driver. Review the path before comparing the figures.

## Validate the structure

Use business knowledge to check whether the graph is plausible. Look for expected relationships that are absent, unexpected paths, and variables with incoming or outgoing effects that do not match how the business operates.

The graph represents the structure and assumptions used by the model. It should be reviewed with Diagnostics and Contribution, not interpreted as standalone proof.

## Causal evidence in Contribution

Contribution can display a causal status for a channel or tactic. **Confident** indicates stronger causal support. **Watch** indicates lower confidence and requires additional review. A dash indicates that no causal status is available.

Use Graph to inspect the relevant paths, then check uncertainty and model behavior before acting on the estimate.

**\[VIDEO PLACEHOLDER: Selecting a node and tracing direct and indirect effects]**
