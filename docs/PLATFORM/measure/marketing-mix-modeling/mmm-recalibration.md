---
title: Model Retraining
excerpt: >-
  Modify input data, model parameters, and relationships to create a new model
  from an existing model
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Over time, a model's predictive power naturally decreases. The patterns it learned from its original training data can become less relevant as it encounters new, evolving information from the real world—a phenomenon known as model drift.

However, gradual drift isn't the only reason a model may need an update. Significant business changes also demand that your model adapts to maintain its relevance and accuracy. To ensure your data-driven decisions remain impactful, it's crucial to evaluate if your model is still aligned with your current business reality.

### Reasons to Retrain a Model

Consider retraining your model based on the following factors:

* **Model Drift:** As the statistical properties of your incoming data shift, a model's performance can degrade. Our platform helps you stay ahead of this by using a built-in drift detection algorithm. This system continuously monitors the model's accuracy on new data and will automatically alert you when significant drift is detected, suggesting that it's time for a new model.
* **Business and Strategic Alignment:** Your models must evolve with your business goals. Retraining is essential to ensure your model's insights remain impactful when your strategies change. For instance, you should retrain your model after:
* **Launching new products** to incorporate their data and measure their impact.
* **Investing in new marketing channels** to accurately assess their effectiveness.
* **Shifting core business priorities**, which may require the model to optimize for different outcomes.

<br />

## How to perform a model retraining

<Image align="center" src="https://files.readme.io/3fc8078846a248e70434eccf53391841fcb970939ae5382d33af8d091403aba1-reconfig.jpg" />

1. Navigate to the model you want to Retrain from the MMM page.
2. Click the ‘Retrain’ button on the top right corner.
3. Follow the same process as creating a new model [creating a new model](https://docs.lifesight.io/update/docs/model-creation#/)
4. Click on ‘Finish’.
5. A new model is created with the status "Training in Progress" in the MMM dashboard.
6. Once the Refresh is completed, the status changes to "Success" in the MMM dashboard.

<br />

## When to Create a New Model

### Model Stability

* **Consistent Spending:** If your media spend remains relatively stable over a period, a model refresh might provide similar insights to the previous model. However, regular refreshes are still recommended to account for market fluctuations and potential model drift.

### Model Adoption

* **Significant Spending Changes:** If you've made substantial changes to your spending across channels, the model's insights might deviate from previous findings. In such cases, building a new model might be necessary.
* **Market Changes:** Major shifts in the market, such as economic downturns, new competitors, or changes in consumer behavior, can necessitate model updates to maintain accuracy.
* **Product Launches or Changes:** Introducing new products or making significant changes to existing ones can affect sales and require model adjustments.
* **Media Channel Changes:** Adding or removing media channels, or making significant changes to channel strategies, can impact model performance.