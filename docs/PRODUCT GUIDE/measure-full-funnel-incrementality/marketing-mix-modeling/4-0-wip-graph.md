---
title: '[4.0][WIP] Graph'
excerpt: Use causal graph relationships to understand modeled effects.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The **Graph** tab shows the causal structure used by the selected model.

**[IMAGE PLACEHOLDER: Graph tab with a selected node and effect details]**

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

**[VIDEO PLACEHOLDER: Selecting a node and tracing direct and indirect effects]**
