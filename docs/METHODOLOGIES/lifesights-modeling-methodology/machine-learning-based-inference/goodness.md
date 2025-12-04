---
title: Model Accuracy
excerpt: How Lifesight Measures and Ensures Model Accuracy
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Lifesight’s Marketing Mix Modeling (MMM) framework is designed to deliver reliable, causal, and decision-ready insights for marketers. Achieving this requires more than just fitting a regression line — it demands a rigorous, multi-layered approach to accuracy, robustness, and validation.

<br />

Our modeling practice combines:

* Structural Causal Modeling (SCM) to encode business logic, causal hierarchies, and guardrails
* Regularized Regression (Ridge) for stable coefficient recovery
* Evolutionary Hyper-Parameter Tuning to search across 100,000+ candidate solutions
* Bootstrapping & Confidence Intervals to quantify uncertainty and ensure reliability

At the end of this process, Lifesight consistently recovers true incrementality and coefficients within a 95% confidence interval.

To communicate and ensure accuracy, we rely on two complementary buckets of evaluation:

***

## 1. Descriptive Accuracy Metrics

These metrics measure how well the model explains historical relationships.

### **1.1 Goodness of Fit Test (G-O-F-T)**

The Goodness of Fit Test evaluates how well the model’s predicted values align with the actual data. The primary metric is R-square, which represents the proportion of variance explained by the model.

* Range: 0 to 1
* Benchmark: >0.8 is considered strong by industry standards
* Interpretation: Higher R² indicates the model captures the underlying drivers more accurately

**Lifesight computes:**

* Training R² — fit quality on the dataset used for estimation
* Testing R² — fit quality on data unseen during training (out-of-sample)
* Validation R² — performance during hyper-parameter evaluation

**Why this matters**
High R² indicates stability and structural correctness in how the model attributes effects across channels.

<br />

### **1.2 Normalized Root Mean Squared Error (NRMSE)**

NRMSE normalizes prediction errors relative to the scale of the data. Lifesight computes:

* Training NRMSE
* Testing NRMSE

Low NRMSE indicates a tight prediction band and a model that minimizes noise.

### &#x20;**1.3 Overall Estimation Error**

This quantifies the cumulative deviation of predicted vs. actual values across the time series. It helps detect:

* Overfitting
* Underfitting
* Structural bias
* Long-term drift

<br />

### &#x20;1.4 Heteroskedasticity Evaluation (Residual Stability Test)

Heteroskedasticity refers to the presence of non-constant variance in the model’s residuals. In MMM, this often occurs due to:

* Seasonal spikes (e.g., BFCM)
* Channel spending bursts
* Asymmetric response functions
* Nonlinear saturation or diminishing returns
* Structural breaks (product launches, pricing changes, stockouts)

Why Lifesight checks this:
A model with heteroskedastic residuals will produce:

* Biased standard errors
* Unstable coefficient estimates
* Overstated significance
* Incorrect confidence intervals

This directly affects incrementality accuracy and elasticity interpretation.

How Lifesight evaluates it:

* Residual vs. Fitted value plots
* Rolling window residual variance checks
* White / Breusch–Pagan style tests (conceptually, without strict p-value dependence due to ridge regression’s nature)
* Variance clustering detection (peak seasons, promo periods)
* Bootstrapped variance stability across top 100 models

**What Lifesight ensures:**

* Residuals do not systematically widen with the level of spend or sales
* Variance does not cluster excessively during campaign bursts
* Confidence intervals remain meaningful and reliable
* Ridge regularization + evolutionary search dampens error variance inflation

**If instability is detected, Lifesight:**

* Adjusts adstock or saturation priors
* Corrects structural constraints
* Rebalances hyper-parameter search
* Re-runs residual bootstrapping

The outcome is stable, well-behaved residuals, which strengthen causal interpretation and improve coefficient recovery.

***

## 2. Predictive Accuracy Metrics

hese evaluate the model’s ability to predict future outcomes — a stronger test of robustness.

### 2.1 Holdout Accuracy

A certain percentage of data (typically 10–20%) is withheld during training. The trained model predicts this unseen window.

* Measures pure predictive power
* Ensures the model generalizes beyond historical patterns
* Guards against overfitting common in high-dimensional MMM datasets

Holdout accuracy is often the most trusted metric for CFOs and growth leaders.

### 2.2 Short-Term Forecast Accuracy

Lifesight performs a forward prediction (e.g., 4–8 weeks) and compares it to actual realized business outcomes.

This helps answer:

* “If I continue current marketing levels, how accurate is the model’s business forecast?”
* “Does the model capture the correct elasticity and decay dynamics?”

Forecast accuracy validates the temporal stability of the model, not just its historical fit.

***

#### How Lifesight Produces Reliable Results: Evolutionary Modeling + Bootstrapping

Unlike traditional MMM approaches that yield one deterministic model, Lifesight’s pipeline generates:

* 100,000+ candidate solutions through multi-objective evolutionary search
* Top models ranked on R², NRMSE, coefficient stability, saturation realism, decay realism, and causal validity
* The best ~100 models selected for bootstrapping
* Final coefficients, elasticities, incrementality, and ROAS computed as averages
* Uncertainty measured at 2-sigma (95%) confidence intervals

This ensures:

* No single model biases the results
* Noise is averaged out
* Coefficients converge to the true effect size
* Every insight is backed by statistical confidence

***

## Putting It Together: Lifesight’s Accuracy Philosophy

### Accuracy = Fit + Predictability + Stability + Causality

Most MMM products stop at R².
Lifesight goes further by validating:

* Fit (R², NRMSE)
* Predictability (holdout accuracy, forecast accuracy)
* Causal correctness (SCM-based DAG constraints)
* Coefficient stability (evolutionary search + bootstrapping)
* Uncertainty (95% confidence intervals across 100+ top models)

This ensures every insight — whether ROAS, mROAS, elasticity, or budget recommendation — is not only explainable, but statistically reliable and practically useful for business decision-making.
