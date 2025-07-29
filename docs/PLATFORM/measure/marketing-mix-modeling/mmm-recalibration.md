---
title: Model Retraining
excerpt: Learn Why and How to retrain your Marketing Mix Models
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

<Image align="center" src="https://files.readme.io/6eb58053bc744403147ccd9aaeb30f23b1ec850a1c0225c2d57a63d07b69c785-Model_Overview_page.png" />

1. Navigate to the model you want to Retrain from the MMM page.
2. Click the ‘Retrain’ button on the top right corner.
3. Follow the same process as creating a new model [creating a new model](https://docs.lifesight.io/update/docs/model-creation#/)
4. Click on ‘Finish’.
5. A new model is created with the status "Training in Progress" in the MMM dashboard.
6. Once the Refresh is completed, the status changes to "Success" in the MMM dashboard.