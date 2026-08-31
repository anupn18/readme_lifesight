---
title: '[4.0][WIP] Diagnostics'
excerpt: Interpret causal evidence and confidence signals in Marketing Mix Modeling.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
The **Diagnostics** tab helps you evaluate model fit, validation performance, channel transformations, decomposition, and calibration evidence.

**[IMAGE PLACEHOLDER: Diagnostics tab with headline metrics and actual versus predicted outcome]**

## Headline metrics

The available metrics can include Accuracy, Backtest Accuracy, NRMSE, actual outcome, predicted outcome, Estimation Error, and MAPE.

Read these metrics together:

* **Accuracy** summarizes how closely the model follows the observed outcome in the fitted data.
* **Backtest Accuracy** shows performance on the held-out portion of the data.
* **NRMSE** and **MAPE** describe prediction error. Lower values generally indicate a closer fit.
* **Estimation Error** highlights aggregate bias between predicted and actual outcome.

Do not use one threshold as the sole promotion decision. Compare training and backtest performance, then inspect where errors occur.

## Actual versus predicted

This chart compares the observed outcome with the model prediction over time. Enable residuals to see the size and direction of the gap at each point.

Large errors concentrated around a launch, promotion, outage, or market event can indicate missing context. A repeated pattern in residuals can indicate that the model has not captured a systematic effect.

## Backtesting

The backtest table summarizes performance on data that was not used to fit the model. Similar training and backtest performance is stronger evidence of generalization than a strong fitted result with weak backtesting.

## Channel response and carryover

Use the saturation, adstock, and time-to-conversion views to understand each channel's fitted behavior.

* **Saturation** shows how response changes as investment increases.
* **Adstock** shows how media impact decays after exposure.
* **Time to Conversion** separates immediate impact from later carryover.
* **Immediate and Carryover** summarizes that split for the available channels.

Review whether the shapes and timing are plausible for the channel and buying strategy.

## Decomposition

Decomposition separates the predicted outcome into modelled components over time. Use it to assess whether media, baseline, trend, seasonal, and contextual movement aligns with known business conditions.

## Calibration summary

The calibration summary displays the experiment evidence supplied during model creation or retraining. Review the channel, experiment period, incremental efficiency, and confidence alongside the model estimate.

**[VIDEO PLACEHOLDER: Interpreting model diagnostics from fit to decomposition]**
