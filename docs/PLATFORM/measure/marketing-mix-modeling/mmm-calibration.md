---
title: MMM Calibration
excerpt: View the impact of your recent calibration on model accuracy
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Once a model has been calibrated, a Calibration Insights Tab becomes available for the calibrated models. This tab provides detailed information about the calibration process, including:


<Image align="center" src="https://files.readme.io/274878df5301cf510178c51d6ab560b03215abcfd322b5f2c18667156cbbfe7a-calibration_tab.jpg" />


Incorporating Recent Observations: If users want to add recent experimental results or observations, they can only do so after the model has been successfully created. At this point, they can use the `Calibrate` button to add these recent results and recalibrate the model.

<br />

## Why Separate Calibration from Initial Model Creation?

Separating the calibration step from the initial model creation allows for validation backtesting. This ensures that the model is properly trained and validated before calibration. Once calibrated, the model will provide more accurate and actionable insights for the channels and inputs that were calibrated.

## Calibration Input:

The specific channels that were calibrated.

- The start and end dates for the calibration.
- The incremental KPI used as input for calibration, including the spend and confidence percentage.

## Calibration Insights:

These insights compare the initial model with the calibrated model.

- Key Performance Indicators (KPIs), such as channel contribution and spend, are displayed alongside their calibrated percentages. This shows how the model’s predictions have changed after calibration.

The comparison helps the user understand how calibration has affected the model, particularly in terms of channel contribution and how it has shifted after incorporating historical data.

## Refresh Insights vs. Calibration Insights

It's important to distinguish between Refresh Insights and Calibration Insights:

- **Refresh Insights:** These are expected to deliver results that are similar to previous model runs, as they update the model with new data without fundamentally changing its underlying structure.
- **Calibration Insights:** These provide more causal insights, as they incorporate new inputs (from historical or experimental data) and recalibrate the model accordingly. Calibration Insights adjust the model’s insights for specific channels based on these inputs, leading to potentially different results than those seen in Refresh Insights.

## Key Changes in Calibration

The ability to compare initial model predictions with calibrated model predictions for calibrated channels. Insights into spend allocation and incremental KPIs based on historical calibration data, giving users a clearer understanding of how calibration has affected model outputs.

These enhancements are designed to make the model more robust and aligned with real-world data, particularly for channels that have been calibrated using past observations or experiments.

<br />

## Calibration status

| MMM status                                                                                              | Indicator               | Definition                                                                                      |   |
| :------------------------------------------------------------------------------------------------------ | :---------------------- | :---------------------------------------------------------------------------------------------- |---|
|                                                                                                         | Calibration in progress | The model changes to this state when a new calibration is applied.                              |   |
| ![](https://files.readme.io/bcb1415d59eb0308044375c53867cf3fb44184a877f1770457364127fb4fa355-image.png) | Calibration success     | The calibration process is complete and the model now shows new insights in the Calibration tab |   |