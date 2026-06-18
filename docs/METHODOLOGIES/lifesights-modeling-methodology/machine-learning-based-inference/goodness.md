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
Lifesight's Marketing Mix Modeling (MMM) framework is designed to deliver reliable, causal, and decision-ready insights for marketers. Achieving this requires more than just fitting a regression line - it demands a rigorous, multi-layered approach to accuracy, robustness, and validation.

### Our modeling practice combines

Structural Causal Modeling (SCM) to encode business logic, causal hierarchies, and guardrails
Regularized Regression (Ridge) for stable coefficient recovery
Evolutionary Hyper-Parameter Tuning to search across 100,000+ candidate solutions
Bootstrapping & Confidence Intervals to quantify uncertainty and ensure reliability

At the end of this process, Lifesight consistently recovers true incrementality and coefficients within a 95% confidence interval.

A single number can never certify a model. We therefore evaluate every model across several complementary layers, each answering a different question:

- Goodness of fit & error - does the model reproduce what actually happened?
- Residual diagnostics - are the regression assumptions actually satisfied?
- Multicollinearity - can the model separate channels that move together?
- Predictive accuracy - does it hold up on data it never saw?
- Coefficient reliability - are the effects stable and well-bounded?
- Causal validity - do the results respect cause and effect, and agree with experiments?

***

### Goodness of Fit & Error Metrics

These measure how well the model explains and reproduces observed outcomes, both on the data it was trained on and on data held out from training.

**1.1 R-squared (R²) and Adjusted R²**

R² represents the proportion of variance in the outcome explained by the model.

- Range: 0 to 1
- Benchmark: >0.8 is considered strong by industry standards
- Interpretation: higher R² indicates the model captures the underlying drivers more accurately

Lifesight computes:

- Training R² - fit quality on the dataset used for estimation
- Testing R² - fit quality on data unseen during training (out-of-sample)
- Validation R² - performance during hyper-parameter evaluation

We also track Adjusted R², which penalizes the addition of variables that do not genuinely improve the model. A large gap between R² and Adjusted R² is an early warning of over-parameterization.

Why this matters: a high, stable R² across train and test indicates structural correctness in how the model attributes effects across channels - not merely a curve threaded through history.

**1.2 MAPE - Mean Absolute Percentage Error (train, test, and overall)**

MAPE expresses error in the most intuitive way possible: the average absolute percentage by which predictions deviate from actuals. Because it is scale-free, it reads as a plain-language statement of trust - "on average, the model is within X% of what happened."

Lifesight reports MAPE in three views:

- Training MAPE - accuracy on the estimation window
- Testing MAPE - accuracy on the held-out window the model never saw
- Overall MAPE - accuracy across the full modeled period

The relationship between these numbers is as important as the numbers themselves. A low training MAPE paired with a much higher testing MAPE is a classic signature of overfitting - the model memorized the past rather than learning it. Lifesight watches that gap closely. Where low-volume or zero-spend periods would distort a raw percentage, we also consider weighted (WMAPE) and symmetric (sMAPE) variants so the metric stays meaningful.

**1.3 NRMSE, RMSE, and MAE**

Lifesight computes Normalized Root Mean Squared Error (NRMSE) on both training and testing data; normalizing relative to the scale of the data makes errors comparable across models and KPIs. Alongside it we read RMSE, which penalizes large misses more heavily and surfaces volatile weeks, and MAE, which is robust to outliers. Low, balanced error across these measures indicates a tight prediction band and a model that minimizes noise.

**1.4 Overall Estimation Error & Decomposition Checks**

This quantifies the cumulative deviation of predicted versus actual values across the time series, and helps detect:

- Overfitting
- Underfitting
- Structural bias
- Long-term drift

We also run a decomposition sanity check: the sum of every channel contribution plus the baseline should reconstruct actual sales without large unexplained residual mass. A decomposition that does not add up points to a misspecified model regardless of how good R² looks.

***

### **Residual Diagnostics & Model-Assumption Tests**

A regression-based MMM is only trustworthy if the assumptions underneath it hold. The residuals - the part of the outcome the model could not explain - are where those assumptions are tested. Well-behaved residuals are random, centered on zero, constant in variance, and free of leftover structure.

**2.1 Homoskedasticity (Constant-Variance) Check**

Homoskedasticity means the residuals have constant variance across the range of fitted values. Its opposite, heteroskedasticity, is common in MMM and arises from:

- Seasonal spikes (e.g. BFCM)
- Channel spending bursts
- Asymmetric response functions
- Nonlinear saturation or diminishing returns
- Structural breaks (product launches, pricing changes, stockouts)

Why Lifesight checks this: heteroskedastic residuals produce biased standard errors, unstable coefficients, overstated significance, and incorrect confidence intervals - all of which corrupt incrementality and elasticity estimates.

**How Lifesight evaluates it:**

- Residual vs. fitted value plots
- Rolling-window residual variance checks
- White and Breusch–Pagan style tests (read conceptually, without strict p-value dependence given ridge regression's nature)
- Variance clustering detection (peak seasons, promo periods)
- Bootstrapped variance stability across the top 100 models

**What Lifesight ensures:** residuals do not systematically widen with spend or sales, variance does not cluster excessively during campaign bursts, and confidence intervals remain meaningful. If instability is detected, Lifesight adjusts adstock or saturation priors, corrects structural constraints, rebalances the hyper-parameter search, and re-runs residual bootstrapping.

**2.2 Residual Autocorrelation (Independence Over Time)**

Because MMM data is a time series, this week's residual should not be predictable from last week's. Leftover serial correlation usually means real structure - carryover, trend, or seasonality - has been missed and wrongly dumped into the error term.

Lifesight checks for it using:

- The Durbin–Watson statistic (first-order autocorrelation)
- Ljung–Box and Breusch–Godfrey tests (higher-order autocorrelation)
- Residual autocorrelation (ACF) plots

When autocorrelation appears, the fix is structural - revisiting adstock/decay, trend, and seasonality terms - rather than cosmetic.

**2.3 Residual Normality & Unbiasedness**

Two related checks: residuals should average to approximately zero (no systematic over- or under-prediction), and their distribution should be well-behaved. Lifesight inspects this with the Jarque–Bera and Shapiro–Wilk tests and Q–Q plots. Approximate normality supports the validity of confidence intervals; where it is violated, Lifesight leans on bootstrapped intervals rather than parametric ones.

**2.4 Residual Stationarity**

A final residual check uses the Augmented Dickey–Fuller (ADF) and KPSS tests to confirm the residuals carry no remaining trend or unit root. Residual nonstationarity is a strong signal that a slow-moving driver (a trend, a structural shift) has been omitted from the model.

***

### **Multicollinearity Diagnostics**

Marketing channels are frequently planned and flighted together, so their spends move in lockstep - which makes it hard for any model to separate their individual effects. Lifesight diagnoses this explicitly using:

- Variance Inflation Factor (VIF) per variable
- The condition number / condition index of the design matrix

High collinearity inflates coefficient variance and makes estimates lurch with small data changes. Lifesight addresses it through Ridge regularization and, where available, objective strong priors ideally informed by incrementality tests. (See also the Marketing Mix Modeling FAQ on how multicollinearity is handled.)

> **Though in standard regression practices collinear variables are avoided or merged - this is not practical in marketing measurements context. Lifesight's ridge regression handles multicolinearity - however the best practice is to calibrate the model with incrementality experiments**

***

### Predictive Accuracy (Out-of-Sample)

Reproducing history is necessary but not sufficient. The stronger test is whether the model predicts outcomes it never saw.

**4.1 Holdout Accuracy**

Lifesight reports holdout accuracy. A portion of the data (typically 10–20%) is withheld during training, and the trained model predicts this unseen window.

Measures pure predictive power
Ensures the model generalizes beyond historical patterns
Guards against the overfitting common in high-dimensional MMM datasets

Holdout accuracy is often the most trusted metric for CFOs and growth leaders, and it is reported alongside the testing MAPE and R² above.

**4.2 Time-Series Cross-Validation (Backtesting)**

A single holdout can be lucky or unlucky. Lifesight therefore backtests using rolling-origin (walk-forward) cross-validation: the model is repeatedly trained up to a point in time and scored on the next window, advancing through history. This produces a distribution of out-of-sample errors rather than a single score, and exposes whether accuracy is stable or fragile across different periods.

**4.3 Short-Term Forecast Accuracy**

Lifesight performs a forward prediction (e.g. 4–8 weeks) and compares it to actual realized business outcomes. This answers:

"If I continue current marketing levels, how accurate is the model's business forecast?"
"Does the model capture the correct elasticity and decay dynamics?"

Forecast accuracy validates the temporal stability of the model, not just its historical fit.

5. **Coefficient Reliability & Significance**

Accuracy of the prediction is not the same as reliability of the individual effects. Lifesight evaluates each coefficient on:

Confidence intervals - 2-sigma (95%) bounds from bootstrapping across the top models
Stability - how little a coefficient moves across the top 100 bootstrapped models and across data refreshes
Sign and face validity - effects must respect the directions encoded in the DAG and business priors (no negative media effects sneaking in)
Significance - t-statistics and p-values are read with care, because under Ridge regularization classical significance tests have limited interpretability; stability and confidence intervals are weighted more heavily

***

### Causal Validity

Finally, a model can fit and predict well and still be causally wrong. Lifesight validates that results respect cause and effect by enforcing the SCM-based DAG constraints during estimation, and by calibrating the model against incrementality experiments. Agreement (within reason) between the model and a well-run experiment is the strongest available evidence that the estimates are causally sound; a persistent gap is treated as information and feeds the next calibration.

***

How Lifesight Produces Reliable Results: Evolutionary Modeling + Bootstrapping

Unlike traditional MMM approaches that yield one deterministic model, Lifesight's pipeline generates:

- 100,000+ candidate solutions through multi-objective evolutionary search
- Top models ranked on R², NRMSE, MAPE, coefficient stability, saturation realism, decay realism, and causal validity
- The best \~100 models selected for bootstrapping
- Final coefficients, elasticities, incrementality, and ROAS computed as averages
- Uncertainty measured at 2-sigma (95%) confidence intervals

**This ensures:**

- No single model biases the results
- Noise is averaged out
- Coefficients converge to the true effect size
- Every insight is backed by statistical confidence

***

### Putting It Together: Lifesight's Accuracy Philosophy

**Accuracy = Fit + Predictability + Stability + Causality**

Most MMM products stop at R². Lifesight goes further by validating:

- Fit & error (R², Adjusted R², MAPE on train/test/overall, NRMSE, RMSE, MAE)
- Assumptions (homoskedasticity, residual autocorrelation, normality, stationarity)
- Separability (VIF and condition-number multicollinearity diagnostics)
- Predictability (holdout accuracy, time-series cross-validation, forecast accuracy)
- Coefficient stability (evolutionary search + bootstrapping, confidence intervals, sign/face validity)
- Causal correctness (SCM-based DAG constraints, calibration against experiments)

This ensures every insight - whether ROAS, mROAS, elasticity, or budget recommendation - is not only explainable, but statistically reliable and practically useful for business decision-making.
