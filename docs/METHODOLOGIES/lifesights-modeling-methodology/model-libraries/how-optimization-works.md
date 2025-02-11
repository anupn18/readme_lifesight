---
title: How Optimization Works
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Optimization Overview

Optimization refers to the process of **maximizing** or **minimizing** a function relative to a given set of conditions, often representing a range of available choices. This function enables the comparison of various options to determine the best solution.

## Goals of Optimization

### Understanding Modeling Issues:

- **What to look for in setting up an optimization problem?**
- **What features are advantageous or disadvantageous?**
- **What devices/tricks of formulation are available?**
- **How can problems usefully be categorized?**

### Analysis of Solutions:

- **What is meant by a "solution?"**
- **When do solutions exist, and when are they unique?**
- **How can solutions be recognized and characterized?**
- **What happens to solutions under perturbations?**

### Numerical Methods:

- **How can solutions be determined by iterative schemes of computation?**
- **What modes of local simplification of a problem are convenient or appropriate?**
- **How can different solution techniques be compared and evaluated?**

<br />

# Lifesight's Multi-Objective Optimization Approach

At Lifesight, we utilize a multi-objective optimization algorithm for Marketing Mix Modeling (MMM), recognizing that such problems typically involve multiple conflicting objectives. This approach aligns with the understanding that MMM is both a scientific and creative endeavor, where the model must both predict accurately and yield interpretable results. Consequently, this leads to a multi-objective optimization problem.

We have chosen regularized regression as the optimization framework, supported by **TwoPointsDE**, an evolutionary algorithm from Nevergrad, where hyperparameters are optimized through multiple evolutionary iterations, rather than traditional sampling methods like MCMC in Bayesian regression.

## Objective Functions

Lifesight currently employs three key objective functions for hyperparameter optimization:

### NRMSE (Normalized Root Mean Square Error)

This metric quantifies the prediction error. Lifesight enables time-series validation by splitting the dataset into training, validation, and test sets. When time-series validation is not employed, the training error (**nrmse_train**) serves as the objective function during evolutionary iterations. With time-series validation, the validation error (**nrmse_val**) becomes the objective function, while the test error (**nrmse_test**) assesses out-of-sample predictive performance.

### DECOMP.RSSD (Decomposition Root Sum of Squared Distance)

This metric measures the deviation between the share of media spend and the share of media effect, serving as the business error. **DECOMP.RSSD** penalizes models that exhibit extreme discrepancies between these two factors, thereby guiding the selection of models that are more aligned with business expectations. While controversial due to the convergence of media ROAS, it helps balance multiple objectives and narrow down the selection of optimal models.

### MAPE.LIFT (Mean Absolute Percentage Error for Experiment Calibration)

Activated during calibration, this metric minimizes the difference between the predicted effect and the causal effect observed in experiments, aiding in more accurate calibration of models.

## Optimizers

Currently, four types of hyperparameters are optimized in Lifesight’s MMM models:

### Adstocking

Either the theta parameter (for geometric adstocking) or the shape and scale parameters (for Weibull adstocking) are optimized.

### Saturation

The Hill function parameters alpha and gamma are optimized to capture the saturation effects in media spend.

### Regularization

The lambda parameter, representing the penalty term in ridge regression, is optimized to prevent overfitting.

### Validation

The train_size parameter, representing the proportion of data used for training, is also optimized.

## Pareto-Optimality in Model Selection

Using the concept of **Pareto-optimality**, which balances all objective functions, Lifesight outputs a set of Pareto-optimal model candidates considered "best." Each solution is a trade-off between the different objective functions. The Pareto front represents models where no single objective can be improved without worsening another. The accompanying Pareto chart illustrates the trade-off between NRMSE and DECOMP.RSSD, where each point represents an explored model solution, and the lower-left corner contains Pareto-optimal models.