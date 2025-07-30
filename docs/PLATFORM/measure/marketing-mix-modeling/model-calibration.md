---
title: '[WIP] Model Calibration'
deprecated: false
hidden: true
metadata:
  robots: index
---
Model calibration is the process of adjusting the predictions of your Media Mix Model to be consistent with conclusions drawn from incrementality tests. This alignment helps ensure the model's outputs are highly accurate and actionable for marketing decisions.

<br />

### Why Calibrate Your Model?

Calibrating your model helps to

* **Improve Accuracy:** Align model predictions with actual incrementality test results for a more precise understanding of marketing effectiveness.
* **Enhance Actionability:** Ensure the insights from your MMM are directly applicable and reliable for budget allocation and strategic planning.
* **Incorporate Real-World Learnings:** Integrate the nuanced understanding gained from specific experiments into your overarching model.
  <br />

# Accessing Model Calibration

You can calibrate your model at two key stages:

## During Model Creation

Model calibration can be performed while you are initially setting up and training a new Media Mix Model. This ensures the foundational model is robust and aligned from the outset.

![]()

## Calibrating an Existing Model

Calibration can also be done at any point after your model has been fully trained and is operational. This is crucial for continuous optimization and adapting to changing market dynamics or new test results.

<br />

To calibrate an existing model:

1. Navigate to model and click on the **Calibrate** button on the top right
2. To make changes to the model configuration, follow similar steps taken while creating the model.

<br />

### Performing Calibration

Once your model is configured, you can proceed with the calibration process. This involves defining specific parameters for each channel or tactic you wish to calibrate.

1. **Add Calibration Rows:** Click the **Add** button to introduce a new row for calibration input. \[cite: 349]
   2. **Define Calibration Parameters:** For each row, specify the following:\
      **Channel/Tactic:** Select the specific marketing channel or tactic (e.g., Amazon Ads, Google MOF, Snapchat).
      **Start-End Date:** Define the date range for the calibration data (e.g., \{\{CALIBRATION\_START\_DATE}} - \{\{CALIBRATION\_END\_DATE}}).
      **ROAS:** Enter the Return on Ad Spend (ROAS) value for the chosen channel/tactic (e.g., 2.6).
      **Confidence %:** Set the confidence level for this calibration point (e.g., 90%).
      **Calibration Type:** Select the type of calibration (e.g., Coarse Calibration).
      3. **Recalibrate the Model:** After inputting all desired calibration parameters, click the **Recalibrate Model** button to apply the changes and update your model.
   <br />

## Analyzing Calibration Insights

<br />

After calibration, the platform provides detailed insights into how the adjustments have impacted your model's predictions and key performance indicators.

<br />

### Actual vs. Predicted Revenue Chart

This chart visually compares the "Actual Revenue" against the "Predicted Revenue" over time, allowing you to see the model's accuracy after calibration.

<br />

### Calibration Input Table

This table summarizes the inputs you provided for calibration, including Platform, Start-End Date, ROAS, Confidence %, and Calibration Type.

<br />

### Calibration Insights Table

This table presents a detailed breakdown of the calibration's impact across different categories (e.g., Contextual, Paid). It includes:

* **Main Contribution %:** The initial contribution percentage before calibration.
* **Calibrated:** The adjusted contribution percentage after calibration, along with the percentage change.
* **Main KPI:** The original Key Performance Indicator value.
* **Calibrated KPI:** The adjusted KPI value after calibration, along with the percentage change.
* **Main ROAS:** The original Return on Ad Spend value.
* **Calibrated ROAS:** The adjusted ROAS value after calibration, along with the percentage change.
  <br />
  This table helps you understand precisely how the calibration influenced your model's understanding of each category's performance.
  <br />