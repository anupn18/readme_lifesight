---
title: Model Refresh
excerpt: >-
  Lifesight's MMM refresh provides real time MMM insights for agile decision
  making.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
MMM Refresh ensures it continues to provide accurate and actionable insights. A Model Refresh is necessary if the input data fed to the model was using CSV upload or if the integrated data sources don't automatically refresh the model periodically.

<Image align="center" src="https://files.readme.io/53307ad5b29545bca4d65540615b72e2b3b9efa8fa99fb4330ee55d44ef78d8b-refresh.jpg" />

<br />

Key aspects of refreshing a model include:

* **Hyperparameter Adjustment:** The model's settings (hyperparameters) are refined based on the proportion of new data to the total dataset. This helps the model adapt to changes in the market.
* **Objective Function Optimization:** The model is optimized using a combination of metrics to balance accuracy and stability.
* **Baseline Stability:** The refreshed model aims to maintain a similar baseline to the original model, ensuring consistent performance.
* **Media Spend Reflection:** The updated model should accurately capture the impact of media spending changes in the new data period.

**Note:** You can find more about the Refresh Methodology [here](https://docs.lifesight.io/docs/mmm-refresh).

<br />

<br />

<br />

## Overview

* **Refresh** - Shows you the current model refresh version. For example if a model is refreshed twice then the Refresh field would have a value "Refreshed Model-2" in place.
* **Compare to** - Refers to which model you are comparing the latest Refresh model with. By default Lifesight sets it as 'Main Model' to view how the refreshed insights compare with the main model.

<br />

## Actual vs Predicted Revenue

View when a Model Refresh had happened to see changes in actual vs predicted revenue. A successful model refresh would result in better model accuracy after a refresh.

The count of Refresh is indicated by R1, R2, R3 and so on for reference. Each Refresh period is highlighted using different colors.

The Validation period is different and set for backtesting purposes. This can be modified by mentioning the Training Size in the Configuration tab while creating an MMM model.

![](https://files.readme.io/aa94b2a84a732b2ecd423a548432530663f0ef3298d4e470ec409f35a4c7bba6-image.png)

## Refresh Insights

The Refresh insights table shows the latest model refresh insights vs the selected previously selected model insights for every channel and category. Seamlessly view the following metrics:

* **Changes in Contribution** - View how channel and tactic contribution changed after the model refresh.
* **Changes in KPI** - View the latest business KPI (Revenue/Orders...) channel-wise based on the latest contribution percentage.
* **Changes in overall spend** - View the increase spends due to the model refresh.

![](https://files.readme.io/4ca3c4e13bef5756d07e3ef31d3495661899b528ea6f8a7e6a8354723e6a4e2e-image.png)

<br />

## How to manually refresh a model

1. Click the `Refresh` button next to the relevant model on the Marketing Mix Models page.
2. Upload a CSV file with refreshed data that matches the column structure of the original file and contains additional rows.
3. Click on `Finish`

Upon initiating a refresh, the model status will change to 'Refresh in Progress' and later to 'Refresh Success' within 5–10 minutes. The 'last refreshed' column will also be updated to reflect the most recent refresh date. Note that models can be refreshed multiple times as needed.

You can also configure the refresh frequency on the `Configure your model` page during model creation.

![](https://files.readme.io/52431c7c9c0bb284370d2e01e8428848f1e6e21c1a8c5fe7e270601286f4d392-image.png)