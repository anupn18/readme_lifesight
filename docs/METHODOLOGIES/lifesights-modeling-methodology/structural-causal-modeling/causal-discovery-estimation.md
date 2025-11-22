---
title: Causal Discovery & Estimation
excerpt: How Causal Graph is used to estimate incremental effects
deprecated: false
hidden: true
metadata:
  robots: index
---
Once the causal DAG is in place we run a two step process 

* Step 1 : Causal Discovery
* Step 2 : Causal Effect Estimation

The important thing to note here is that these steps are run concurrently with the ML based inference step and not sequentially

While the input data is fed into the causal dag for causal discovery, it's also passed to the ridge regression module for estimation of "direct effects" from those variables

<br />

<br />