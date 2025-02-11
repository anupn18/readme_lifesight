---
title: Bootstrapping
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
# Confidence Intervals and Uncertainty in ROAS/CPA Calculation

## Understanding Bootstrapping

Bootstrapping is a powerful statistical technique to estimate the uncertainty of a metric (like ROAS or CPA) by repeatedly resampling the original data. The basic idea is that by resampling your data, you can generate an empirical distribution of possible outcomes and thereby assess how much your estimate might vary.

### Key Concepts of Bootstrapping:

- **Sampling with Replacement**: In bootstrapping, random samples are taken from the **original dataset** with replacement, meaning that the same observation can be included multiple times in the resampled datasets.
- **Resampling to Estimate Uncertainty**: By repeatedly resampling the dataset, you simulate what it would be like to draw different samples from the population. This allows you to assess how much the estimate might vary if you observed different data.
- **Standard Error Estimation**: Bootstrapping gives a way to compute the **standard error** of a statistic (such as ROAS or CPA). The standard deviation of the bootstrapped estimates is used as an estimate of the standard error.

## Traditional Approach vs. Bootstrap Approach

### Traditional Sampling Distribution:

In traditional statistics, you assume that if you could take all possible samples of a given size from a population, the estimates would form a **sampling distribution**. If the sample size is sufficiently large, the sampling distribution would be approximately **normal** (bell-shaped), and its standard deviation would be the **standard error**.

However, when sample sizes are small, or the data doesn’t follow normality, this assumption breaks down, making it difficult to draw reliable conclusions using traditional methods.

![](https://files.readme.io/4a4b5eecaf22a7d42558ed2f110f9112ae9a756fe6347182453d402e0b67d34d-image.png)

<br />

### Bootstrapping Approach:

Instead of relying on theoretical distributions, bootstrapping constructs an empirical sampling distribution by:

1. Drawing a sample of size **n** from the population.
2. Resampling from that sample **m** times with replacement.
3. Creating a distribution of estimates from these **m** resampled datasets, which mimics the theoretical distribution.

### How Lifesight Implements Bootstrapping:

Lifesight uses bootstrapping to introduce confidence intervals for ROAS and CPA metrics by:

1. **Finding Optimal Models**: 
   - Lifesight calculates ** optimal models**, identifying models that strike the best balance between accuracy and generalizability.
2. **Clustering Models**: 
   - Using clustering techniques such as **k-means**, Lifesight identifies groups of models with similar **hyperparameters**. This ensures that each cluster represents a set of models with comparable behavior across channels.
3. **Bootstrap Sampling**:
   - For each cluster of models and for each channel, Lifesight performs **bootstrap resampling** on the calculated **ROIs**.
   - From this, Lifesight calculates the **confidence intervals** and **standard error** for each channel's ROAS or CPA.

This approach allows for a more robust understanding of how marketing investments perform across channels, offering a deeper level of insight than a single point estimate can provide.

## Benefits of Bootstrapping in ROAS/CPA Estimation:

1. **No Distribution Assumption**: Unlike traditional methods, bootstrapping doesn’t require the assumption that the data follows a specific distribution (e.g., normal distribution). This makes it applicable to datasets of any size or shape.
2. **Empirical Confidence Intervals**: You can directly compute confidence intervals from the resampled data, providing a more accurate estimate of the uncertainty in your ROAS/CPA.
3. **Handling Variability Across Channels**: Bootstrapping accounts for variability in channel performance, making the derived ROAS or CPA metrics more reliable and reflective of the true performance.

## Conclusion:

Bootstrapping in Lifesight offers a robust way to measure the uncertainty in ROAS or CPA calculations. By resampling the data and calculating empirical confidence intervals, Lifesight provides more reliable estimates, giving users deeper insights into the performance of their marketing channels.