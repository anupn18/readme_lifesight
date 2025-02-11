---
title: MMM Recalibration
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
## How to perform a model reconfiguration

<Image align="center" src="https://files.readme.io/3fc8078846a248e70434eccf53391841fcb970939ae5382d33af8d091403aba1-reconfig.jpg" />

1. Navigate to the model you want to Reconfigure from the MMM page.
2. Click the ‘Reconfigure’ button on the top right corner.
3. Enter the model name, map data inputs to Platforms for the MMM model to understand the data.
4. Click on ‘Finish’.
5. A new model is created with the status "Training in Progress" in the MMM dashboard.
6. Once the Refresh is completed, the status changes to "Refresh Success" in the MMM dashboard.

<Image align="center" src="https://files.readme.io/d9ced717fec1fc08d10c7539d5d104da98cee69a70a98c429e8168cd3e2b01e3-resfresh_status.jpg" />

***

## How It Works

* Our refresh function takes an existing model as a starting point and updates it using new data. 
* Key aspects of this process include:
  * **Hyperparameter Adjustment:** The model's settings (hyperparameters) are refined based on the proportion of new data to the total dataset. This helps the model adapt to changes in the market.
  * **Objective Function Optimization:** The model is optimized using a combination of metrics to balance accuracy and stability.
  * **Baseline Stability:** The refreshed model aims to maintain a similar baseline to the original model, ensuring consistent performance.
  * **Media Spend Reflection:** The updated model should accurately capture the impact of media spending changes in the new data period.

**Note:** You can find more about the Refresh Methodology [here](https://docs.lifesight.io/docs/mmm-refresh).

## When to Create a New Model

### Model Stability

* **Consistent Spending:** If your media spend remains relatively stable over a period, a model refresh might provide similar insights to the previous model. However, regular refreshes are still recommended to account for market fluctuations and potential model drift.

### Model Adoption

* **Significant Spending Changes:** If you've made substantial changes to your spending across channels, the model's insights might deviate from previous findings. In such cases, building a new model might be necessary.
* **Market Changes:** Major shifts in the market, such as economic downturns, new competitors, or changes in consumer behavior, can necessitate model updates to maintain accuracy.
* **Product Launches or Changes:** Introducing new products or making significant changes to existing ones can affect sales and require model adjustments.
* **Media Channel Changes:** Adding or removing media channels, or making significant changes to channel strategies, can impact model performance.

## Determining the Need for a New Model

To determine if a new model is necessary, consider the following factors:

* **Model Drift:** Model drift occurs when the underlying patterns in the data that a model was trained on begin to shift over time. This can lead to a decline in the model's predictive accuracy. To mitigate this, we incorporate a drift detection algorithm that continuously monitors the model's performance against new data. If significant drift is detected, the platform suggests creating a new model.
* **Alignment of Insights and Business Objectives:**
  * Introducing new products, exploring fresh marketing channels, or shifting business priorities can render existing models outdated. To maintain accuracy, models must adapt to these changes. 
  * New product launches, for instance, require incorporating fresh data to capture their impact. Similarly, spending on novel marketing channels necessitates model updates to accurately assess their effectiveness. 
  * By continuously evaluating a model's alignment with business goals and making necessary adjustments, organizations can ensure data-driven decisions remain relevant and impactful.
