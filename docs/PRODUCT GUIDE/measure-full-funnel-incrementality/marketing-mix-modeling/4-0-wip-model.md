---
title: '[4.0][WIP] Model Attributes'
excerpt: Understand the attributes and configuration of a Marketing Mix Model.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The **Diagnostics** tab in Lifesight 4.0 helps you evaluate model performance, validation quality, and the transformations applied to each channel.

**[IMAGE PLACEHOLDER: Diagnostics tab showing model fit health and actual versus predicted outcome]**

## Model Fit Health

The health summary evaluates a set of model-quality checks and classifies each check as **Pass**, **Warn**, or **Fail**. Use the overall verdict to understand whether the model is healthy, requires monitoring, or needs action before it is used for decisions.

Expand **Troubleshoot** to review likely causes and recommended actions for checks that need attention.

### Common Diagnostic Metrics

* **Accuracy:** In-sample fit accuracy between the modelled and actual outcome.
* **NRMSE:** Normalized Root Mean Squared Error. Lower values indicate a closer fit.
* **MAPE:** Mean Absolute Percentage Error across time periods.
* **R-squared:** The proportion of outcome variance explained by the model.
* **Estimation Error:** Aggregate bias between total predicted and actual outcome.
* **Backtest Accuracy:** Performance on a holdout period that was not used for training.
* **Holdout MAPE:** Prediction error on unseen data.
* **Decomposition Residual:** The gap between the actual outcome and the sum of modelled components.
* **Coverage:** How often the actual outcome falls within the model's confidence interval.
* **Stability:** How consistently channel coefficients behave across validation runs.

> 📘 Metric availability depends on the model output. Review the displayed threshold and description rather than relying on one metric in isolation.

## Actual Versus Predicted Outcome

The chart compares the observed KPI with the model's prediction across the training and validation periods. Enable residual analysis to see when and where the prediction differs from the actual result.

### Backtesting

Backtesting evaluates the model against a holdout period. The training-size setting chosen during model creation determines how much of the dataset is reserved for validation.

Consistent performance on unseen data provides stronger evidence that the model can support forecasting and planning.

**[IMAGE PLACEHOLDER: Actual versus predicted chart with training, validation, and residual views]**

## Saturation and Adstock Curves

Select a channel to inspect its fitted response and carryover behavior.

* **Saturation Curve:** Shows how incremental response changes as spend increases and approaches diminishing returns.
* **Adstock Decay:** Shows how the effect of media persists after the original exposure.
* **Time to Conversion:** Separates immediate impact from carryover impact across later periods.

## Time Series Decomposition

The additive decomposition separates the outcome into components such as baseline, media, trend, seasonality, and holiday or event effects. Use it to identify whether major changes in the KPI are explained by marketing or by non-media factors.

**[IMAGE PLACEHOLDER: Saturation, adstock, time-to-conversion, and decomposition charts]**

## Recommended Review Order

1. Start with the health verdict and failed checks.
2. Review actual versus predicted performance in training and validation periods.
3. Inspect residuals for concentrated errors or missing events.
4. Review channel transformations and carryover assumptions.
5. Confirm that the decomposition is plausible for the business.
6. Use the Contribution and Graph tabs before promoting the model to a decision.

**[VIDEO PLACEHOLDER: Reviewing model diagnostics in Lifesight 4.0]**
