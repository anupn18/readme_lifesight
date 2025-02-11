---
title: Model convergence
excerpt: Understanding Model Convergence in Marketing Mix Modeling
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Introduction

In the dynamic world of marketing mix modeling, determining when a model has reached convergence is crucial for ensuring reliable results. At Lifesight, we employ specific criteria to assess model convergence, enabling us to provide accurate insights to our clients. 

***

## What is Model Convergence?

Model convergence refers to the point at which further iterations of the optimization process no longer yield significant improvements in the model's performance. In essence, it's when the model has discovered a stable solution that best fits the data.

***

## Lifesight's Convergence Criteria

At Lifesight, we utilize two primary criteria to determine if a model has converged:

### 1️⃣ Criterion 1: Standard Deviation Stability

We compare the standard deviation of the last quantile to the mean standard deviation of the first three quantiles. The model is considered to be converging when:

> 📐 **Last quantile's standard deviation \< First 3 quantiles' mean standard deviation**

This criterion ensures that the variability in the model's performance has decreased and stabilized over the course of the optimization process.

### 2️⃣ Criterion 2: Absolute Performance Threshold

We assess the overall improvement in performance by comparing the last quantile to the first quantile. The model is considered to be converging when:

> 📏 **Last quantile's absolute median \< Absolute first quantile's absolute median - 2 \* First 3 quantiles' mean standard deviation**

This criterion ensures that the model's performance has significantly improved from its initial state, reaching a predefined threshold of excellence.

***

## Understanding Quantiles 

In our methodology, we divide the total number of model iterations into quantiles:

- At Lifesight we run 5000 iterations for each model, so each quantile represents 1250 iterations
- First quantile: iterations 1-1250
- Second quantile: iterations 1251-2500
- And so on...

This division allows us to track the model's progress and performance over time, providing a clear picture of its convergence path.

***

## Key Performance Metrics 

We focus on two crucial performance metrics:

1. **NRMSE (Normalized Root Mean Square Error)**
   - Measures the model's overall error
   - Crucial for assessing model quality
   - Lower values indicate better model fit

2. **CIDI (Channel Impact Divergence Index)**
   - Quantifies the allocation of effects between different marketing channels
   - Indicates how "radical" the model's recommendations are
   - Lower values suggest more balanced channel impact predictions

***

## Interpreting Convergence Results

- Both criteria must be satisfied for full model convergence
- Greater emphasis on NRMSE convergence (direct reflection of model accuracy)
- CIDI convergence interpreted cautiously:
  - Low CIDI ≠ Necessarily better model
  - Low CIDI = Less extreme recommendations for spend and effect allocation
- Continuous monitoring: Convergence is an ongoing process, not a fixed endpoint

***

## Example Scenario 

Consider a 50/50 investment split between channels A and B:

| Model | Channel A Effect | Channel B Effect | CIDI   | Interpretation                             |
| ----- | ---------------- | ---------------- | ------ | ------------------------------------------ |
| 1     | 100%             | 0%               | High   | Extreme allocation, potentially overfit    |
| 2     | 50%              | 50%              | Low    | Balanced allocation, potentially underfit  |
| 3     | 70%              | 30%              | Medium | Moderate allocation, potential optimal fit |

> 💡 The optimal model balances between fitting the data well and providing actionable insights.

***

## Conclusion

Understanding model convergence is pivotal for interpreting marketing mix model results. At Lifesight, our criteria ensure reliable and actionable insights. However, remember that convergence metrics are indicators, not absolute measures of model quality. Always consider the underlying data, model structure, and business context when interpreting results.

Key takeaways:

- Monitor both NRMSE and CIDI for comprehensive convergence assessment
- Interpret results in the context of your specific marketing ecosystem
- Convergence is a journey, not a destination - continuous refinement is key

By mastering these concepts, you'll be well-equipped to leverage Lifesight's marketing mix models for optimal decision-making and resource allocation.

***