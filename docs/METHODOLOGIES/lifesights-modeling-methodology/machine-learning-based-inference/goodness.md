---
title: Accuracy
excerpt: Understand how models are measured for goodness of fit
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Average ( Top 100 models with lowest training NRMSE, lowest testing NRMSE, highest validation R2). Confidence ascertained at 2 Sigma standard deviation

***

### Goodness of Fit Test (G-O-F-T)

**What is G-O-F-T:**  
The Goodness of Fit Test measures how well the model’s predictions match the actual data. In simple terms, it indicates the proportion of the model explained by the independent variables (e.g., price, media, promotions). It is typically measured by R-square.

**Why is G-O-F-T Needed:**  
To evaluate the fit of the trend line for actual versus predicted values. A good fit suggests that the model is effective for understanding and predicting the impact of marketing activities on business outcomes.

**Range of R-square:**  
The value of R-square ranges from 0 to 1. A value closer to 1 indicates a better model. According to marketing standards, R-square should be greater than 0.8 (or 80%).

<Image align="center" border={true} width="1px" src="https://files.readme.io/8132facbbb350d541b953a1a90f03193d2958f5b08c782e7af3ede32d11e7f1e-image.png" className="border" />

<Image align="center" border={true} src="https://files.readme.io/ea1b30150a27cce8abf894f633e42f71bbebcc7b75dc90cbacdba9519bae6d72-image.png" className="border" />

<br />

### Significance of Goodness of Fit Test

**Model Accuracy Evaluation:**

* **Purpose:** The G-O-F-T helps determine how well a model's predictions align with the actual observed data.
* **Importance:** Accurate models provide reliable insights and forecasts, which are essential for effective decision-making. In MMM, for example, this could mean understanding the true impact of marketing activities on sales.

**Assessing Model Validity:**

* **Purpose:** It verifies whether the model appropriately represents the underlying data structure and relationships.
* **Importance:** A valid model accurately reflects real-world phenomena and avoids misleading conclusions. This is critical for making informed strategic decisions based on the model's output.

**Improving Model Refinement:**

* **Purpose:** The test identifies how well the model captures variations in the data, helping in refining and improving the model.
* **Importance:** By understanding the fit, you can adjust or enhance the model, such as adding relevant variables or modifying assumptions, to better capture the dynamics of the data.

**Comparing Different Models:**

* **Purpose:** It allows for the comparison of different models to determine which one provides a better fit.
* **Importance:** In MMM, comparing models helps in selecting the best model for predicting outcomes and evaluating marketing strategies, leading to more effective resource allocation.

**Quantifying Model Performance:**

* **Purpose:** Metrics like R-square, Adjusted R-square, and MAPE provide quantitative measures of the model's performance.
* **Importance:** These metrics help in understanding the proportion of variance explained by the model and the accuracy of predictions, guiding decisions based on statistical evidence.
