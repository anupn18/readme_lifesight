---
title: Model Calibration
excerpt: Improve model estimates from high power experiments
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Calibration in Marketing Mix Modelling (MMM)

**Calibration** is a critical process that adjusts the model's predictions to align more closely with causal experiments. While MMM uses historical data to estimate the impact of marketing activities, calibration ensures that these predictions are accurate and consistent with more precise experiments.

## Why Calibration is Important

Calibration improves the reliability of MMM by adjusting model predictions based on external benchmarks, which can include:

* **Experimental Data**: Results from A/B tests, randomized controlled trials (RCTs), or geolift scale up or holdout experiments provide a "ground truth" for how marketing activities drive outcomes. If the model's predictions differ from these results, calibration can adjust the estimates to better reflect reality.
* **Platform conversion lift studies** : Many platforms (e.g., Facebook, Google, YouTube) provide their own conversion lift studies . The results of these studies can be used for calibration as well.

<br />

## How to know which channels/tactic to Calibrate :

<br />

**Attribute Quality Score** :

Our **Attribute Quality Score Methodology** helps identify which channels or tactics require calibration to improve accuracy and performance. The methodology assesses several key factors:

* **Spend Variation:** Does the `channel/tactic` exhibit enough variation in spend to generate meaningful insights?
* **Quantification in the MMM Model:** Is the channel accurately represented in the MMM model? This is evaluated by:
  * **ROI Estimation:** Can we estimate the ROI with confidence?
    * If the channel's contribution is `0%`, we recommend conducting experiments to gather more data.
    * If the ROI estimates show a wide standard error or confidence interval, it indicates the need for calibration to enhance estimate accuracy.

After running an MMM model, the **Attribute Quality Score** provides guidance on which channels to prioritize for experimentation.

_Note - Though Lifesight generates right hypotheses which should be tested - so as to improve the overall measurement efficacy - marketers can come with their own hypotheses and get them validated through Lifesight's experiments module_

### Types of Experiments

You can conduct various types of experiments to gather better insights , some of the experiments are mentioned below :

* Geolift experiment.
* Split Testing.
* Conversion Lift Studies.
* A/B Testing.

<br />

> 📘 **Note**: Lifesight offers three types of experiments: Geo Lift, Split Testing, and Time Testing. You can learn more about these experiments here.

## Key Benefits of Calibration

1. **Aligning with Real-World Observations**: Calibration ensures that the model's predictions reflect actual performance by adjusting estimates based on external validation points.

2. **Improving Prediction Accuracy**: MMM estimates are sometimes biased due to data limitations or model assumptions. Calibration corrects these biases, leading to more reliable predictions of marketing effectiveness.

3. **Better Incrementality Estimation**: Calibration ensures that incrementality metrics produced by the model align with more precise experimental or real-world data, resulting in more accurate insights into the true impact of marketing efforts.

4. **Enhancing Trust in Model Outputs**: By adjusting for external data, calibration increases confidence in the model's outputs, allowing stakeholders to trust the insights provided by MMM for better decision-making.

<br />

## Lifesight's Unique Approach to Calibration

Lifesight's approach to model calibration is unique in the industry. We refer to this as Holistic & Contextual Calibration.  Depending on the scenario our platform auto-applies the right approach for model calibration.

**Holistic Calibration**

In Holistic calibration, hyper-parameters are picked so as to minimise the distance between **MMM Inferred Lift** and the actual **Causal Lift** obtained from the experiment. This acts _similar_ to setting a prior and retraining the model.

**MAPE (Contextual) =[Sigma ( |ROI from MMM - ROI from Lift| )] / N**

Holistic calibration is applied in these scenarios

1. When the calibration period is outside of the model's training window.
2. When user wants to apply calibration based on "Go Dark" experiments, when the spend for the period of testing for the whole platform is zero
3. For New Channels (Or channels which has zero or near zero contribution in MMM)

**Contextual Calibration**

This is the recommended approach to calibration (wherever possible). In this approach, Lifesight's calibration function minimises the distance between  **MMM Inferred Lift** and the actual **Causal Lift**  _for the specific period of testing_

**MAPE (Contextual) =[Sigma ( |ROI from MMM,k - ROI from Lift,k| )] / N**  
_(where k is the period(s) for which calibration is applied)_

Contextual Calibration is applied in these scenarios

1. When calibration period is in within the training period of model
2. Platforms / Channels that are calibrated is significant and already has some contribution reported by MMM

***

<Image align="center" border={false} src="https://files.readme.io/0d35ff510f2000f455b2a7b37a6ac9d4a0ac6d6fa0340a2d9971b4a23b710a91-uc.jpg" />
