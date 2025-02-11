---
title: Causal Graph
excerpt: View your Causal model through the DAG
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Once the model's status transitions to "success," the Causal Graph will be accessible to users to view insights. The Causal Discovery Graph incorporates filtering options to refine the visualization based on the significance and confidence of causal relationships

## Causal Discovery Graph

The Causal Discovery Graph is depicted as a Directed Acyclic Graph (DAG), where each node represents a variable, and each directed edge indicates a causal relationship between variables. The graph visualizes the relationships between different variables (e.g., marketing spends, events) and how they potentially affect a target variable (in this case, Revenue_Size_Rupiah). Arrows between nodes represent causal relationships, indicating the direction and strength of the effect between variables.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/589b22bfc81d103d547513345980c2f09a44cb51ae5c5bbfc1145b0350993e93-dag.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


## Graph Filtering Menu

### Edge Weight Threshold

This helps filter connections (edges) between variables based on their weight (importance). The higher the threshold, the fewer connections will appear on the graph, showing only the most significant relationships. Utilizes ATE values to filter causal relationships based on their impact. A slider allows for adjustment from minimum to maximum ATE values, facilitating the focus on significant relationships.

### Edge Confidence Threshold

Adjust the confidence level of the edges (causal relationships) shown in the graph. Increasing the confidence threshold displays only the relationships that are statistically more certain. Determines the reliability of causal predictions. Setting a threshold filters out predictions below a certain confidence level, ensuring decisions are based on robust insights.

### Relationships

View a list of relationships between variables, categorized into different types (e.g., potential or forbidden).The variables on the left side of the arrow represent the cause, and the variable on the right represents the effect. 

_For example, digital_spend → Revenue_Size_Rupiah suggests that digital spending potentially influences revenue size._

### ATE (Average Treatment Effect)

A metric shown next to each edge that quantifies the expected effect of one variable on another, assuming a causal relationship. Positive ATE values indicate a positive effect (increased value), while negative values indicate a reduction in the outcome variable.

## Conf (Confidence):

The confidence score is associated with the causal relationship, ranging from 0 to 1. A higher confidence score indicates more robust evidence supporting the causal link between the variables.