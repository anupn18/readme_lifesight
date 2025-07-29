---
title: Model tab
excerpt: Understand your MMM model accuracy and performance
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Model tab gives insights into your MMM model accuracy and performance.

<br />

<Image align="center" src="https://files.readme.io/b2d7d6fa3178a762ffba6c76234a16026fc5679984753037fe31b2ccdfff0ceb-Screenshot_2025-07-22_at_5.12.19_PM.png" />

***

<br />

## Summary

<Image align="center" src="https://files.readme.io/72f557dd63670b10bd725afa9229fea81bf42be21dae9d03b8af66a633610307-Screenshot_2025-07-22_at_5.13.31_PM.png" />

<br />

* **Accuracy**\
  The model's accuracy is calculated based on how the model's predictions have performed on the last 4 - 12 weeks of unseen data points. This method of accuracy calculation is known as Median Holdout Accuracy.
* **NRMSE (Normalized Root Mean Squared Error):**\
  The Normalized Root Mean Square Error is also referred to as the prediction error indicates how accurate the model’s predictions are. Lower values represent more accurate predictions. It measures the square root of the average squared differences between predicted and actual outcomes.
* **Actual Revenue:**\
  The real revenue generated during a specific period.
* **Predicted Revenue:**\
  The revenue estimated by the model based on input data.
* **Estimation Error (%):**\
  The percentage difference between the actual and predicted revenue, showing how far off the model's predictions are from reality.

<br />

## Actual vs Predicted Revenue chart

![](https://files.readme.io/f229d559d2d40c3949a7c98a9a76614f6445d06e6bfd46983356387d54a9c7b2-image.png)

Validation is a critical step in ensuring the accuracy and reliability of your marketing mix model (MMM). This process tests the model's ability to predict outcomes based on unseen data, providing confidence in its forecasts and insights.

### Backtesting

Backtesting is a key component of the validation process. This method involves removing a portion of historical data and training the model up to a certain point in time, such as three months ago. The model is then asked to forecast outcomes for the next three months. While the actual data for these months is known, the model has not seen it, allowing for a comparison between the model’s predictions and the actual outcomes.

Modify the `Training size` while creating the model to adjust the backtesting period.

<Image align="center" className="border" border={true} src="https://files.readme.io/0cc2a82d07c1c837a3abfea67d12f1c4803586ece4ee2441ac9e5b3cbe13a66c-Backtesting_Accuracy.png" />

Additionally, if the model can consistently make accurate predictions over time, even with changes in marketing budget and other interventions, it provides strong evidence that the model has effectively captured the true causal signals.

### Validation Insights

A summary of the insights from all tests conducted over the last quarter is available. The data is presented in intervals of the last 4 weeks, 6 weeks, 8 weeks, 10 weeks, and 12 weeks. These insights include:

* **Predicted Revenue or Predicted Conversions:** The outcomes forecasted by the model.
* **Actual Revenue or Actual Conversions:** The real-world results during the validation period.
* **Estimation Error (%):** The percentage difference between the predicted and actual outcomes.

By examining these insights, you can evaluate the model's accuracy and make necessary adjustments to improve its predictive capabilities.

<br />

## Saturation and Ad Stock curves

View the conversion distribution for every ad channel using ad stock and saturation hyperparameters. Select the `Filter` dropdown to view ad stock, saturation and time to conversion for a channel.

![](https://files.readme.io/986fe5dbc457fc2f162918b6cb8bd7f460b22f2fe9225a34f26ea783d7080f55-image.png)

<br />

### Ad Stock chart

It represents the carryover effect of each media variable (paid & organic). A common hypothesis of adstock is that offline channels have stronger the carryover.

### Saturation Curve

The saturation curve shows how the incremental impact of a marketing effort decreases as the level of that effort increases. Saturation points represent the point at which additional investment in a particular marketing activity, such as advertising or promotions, will no longer result in a proportional increase in sales or revenue.

### Time to Conversion

View the immediate and carryover conversion effect distributed over time. The chart shows the percentage impact of a channel ad spend on conversions. This helps understand both short-term and long-term impact of ad channels on conversions to help make media optimization decisions.

![](https://files.readme.io/95d6e558893e8422e2df16ada3d4bea5d410380b18edd1951934132fa935c0b4-image.png)

<br />

# Immediate VS Carryover effect chart

![](https://files.readme.io/52ff6d249a5bebed38255c1783532ccb5dcef25835fd81d7bdb9e7cc8f00bb6a-image.png)

This chart breaks down the impact of media spending on revenue into two distinct categories: Immediate and carryover contributions. It allows you to discern when the majority of a campaign's effects are realized.

* **Immediate Contribution:** This refers to the percentage of direct effect of media spending within the same period it is spent. For instance, if an advertisement runs in week 1 of June, the immediate contribution is the revenue directly generated from this advertisement in week one of June itself.
* **Carryover Contribution:** This involves the percentage residual effects of past media spending that continue to influence revenue beyond the initial period of the spend. This phenomenon is also known as adstock. Conceptually, carryover effects are similar to brand equity metrics such as ad recall or campaign.

<br />

## Time Series Decomposition (Additive)

Time series data includes components like seasonality, trends, and holidays that impact conversions. This breakdown helps marketers understand how these factors influence MMM results before modeling. You can view these components and choose whether to include them in future models. Additionally, it aids in setting the base period when using the Planner for forecasting.

![](https://files.readme.io/960af9cf18aa58c1c6268d49e5bb1cf94bc1e89fac4692546c36f0e6874aa76c-image.png)