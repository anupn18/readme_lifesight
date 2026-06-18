---
title: FAQ
excerpt: Frequently asked questions about our modeling practices
deprecated: false
hidden: false
metadata:
  robots: index
---
### Why call it Causal MMM - isn't MMM correlational?

MMM is built using a regression process, and regression is often assumed to be purely correlational. Under the right conditions, however, regression coefficients can be interpreted causally. A coefficient reveals the association between a variable and the outcome when every other variable is held constant, and in a properly specified model these coefficients are average treatment effects rather than mere associations.

This is where the modeling structure matters. Lifesight's modeling starts with a Directed Acyclic Graph (DAG) that captures the data-generating process and learns the nested dependencies between variables. Building the model on that causal structure - rather than throwing every variable into a flat regression - is what allows the coefficients to carry causal meaning.

On top of this, Lifesight supports calibration of the MMM with causal experiments, anchoring the model's estimates to interventional truth.

### If we already have MMM, why is a separate forecasting system needed?

Regression is fundamentally a tool for interpolation: it understands the coefficients of the variables it has seen, and given input data for future periods it can do some extrapolation as well. The hard problem in business forecasting is handling the autoregressive part of the outcome.

The baseline - intercept, trend, and seasonality - is autoregressive, and it typically constitutes anywhere between 30% and 70% of your outcome. Because so much of the total sits in the baseline, strong demand forecasting needs the support of a dedicated forecasting system rather than regression alone. At Lifesight this is handled by an ensemble forecasting engine, disciplined by the causal model so it never forecasts returns the saturation curves rule out.

### How does Lifesight handle multicollinearity?

Multicollinearity - when two or more inputs move together so closely that their individual effects are difficult to separate - is handled with ridge regularization. Where stronger outside knowledge is available, we can also calibrate a variable using objective, strong priors, ideally informed by incrementality tests.

### Does Lifesight support modeling at the geography level?

Yes. Lifesight supports modeling across multiple dimensions. The framework is built to perform multi-dimensional runs, creating models across geographies, product SKUs, and sales channels all in one shot, and then interpreting or aggregating the results back to a specific group of geographies, or a specific combination of product and sales channel, and so on.
