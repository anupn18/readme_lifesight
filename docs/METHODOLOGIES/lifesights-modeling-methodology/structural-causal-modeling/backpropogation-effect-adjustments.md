---
title: Backpropogation & Effect Adjustments
excerpt: >-
  How effects are back-propogated to get the indirect effect and the true total
  effects
deprecated: false
hidden: true
metadata:
  robots: index
---
Before we start this step, we have successfully completed these two :

1. FCI based Causal Discovery based on the Causal Graph
2. Ridge Regression based Direct effect estimation (A detailed view of this approach can be seen <Anchor label="here" target="_blank" href="https://docs.lifesight.io/update/docs/machine-learning-based-inference#/">here</Anchor> )

***

The outcome of the above two steps are there 

Step 1 - Let us assume we started with a DAG , that looks like this : 

<Image border={false} />

<br />

Step 2 - Apply Causal Discovery on this and we get to know the strength of these relationships

<br />
