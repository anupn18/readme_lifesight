---
title: 'Geo Experiments : Power Analysis'
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Statistical power is a crucial element in hypothesis testing, as it measures the ability to detect a real difference between test and control groups. A higher power means a lower likelihood of false negatives, where a true effect goes undetected. Typically, we aim for a power level above 80%, which ensures a reasonable chance of identifying an effect when it exists.

**Components of Power Analysis**

**Statistical Significance Threshold (α)**\
In Geo Experiments, stricter thresholds (e.g., α = 0.05) are often used to account for spatial correlations and reduce the risk of erroneous conclusions across regions.

**Minimum Detectable Effect (MDE)**\
The smallest effect size is deemed meaningful for decision-making. Effects below this threshold may be dismissed as noise, especially given the inherent variability in geographic data.

**Number of Geographic Units**\
Power increases with more test and control regions. A synthetic control method aggregates geographic units to create a robust counterfactual, it's worth noting that limited regions constrain the ability to isolate small effects.

**Power Analysis - Process**\
Unlike traditional tests, Geo Experiments on Lifesight simulate experiments on historical data to estimate a Minimum Detectable Effect (MDE) before launching a live test. A sample sequence of steps is described below:

Step 1: Remove the most recent X (configurable) data points to simulate a “test period”.

Step 2: Use earlier data to build a synthetic control—a weighted combination of control regions that mirrors the test group’s pre-treatment behavior.

Step 3: Apply a hypothetical lift (e.g., 5%) to the test regions during the “removed” month and assess whether a reliable effect can be detected against the synthetic control.

This process quantifies how large an effect must be to achieve high power (e.g., 80%) under real-world conditions, accounting for geographic heterogeneity and temporal trends. By iterating over different effect sizes, the power analysis process helps identify the MDE that balances practical relevance and statistical feasibility.