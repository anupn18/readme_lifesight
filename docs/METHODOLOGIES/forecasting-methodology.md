---
title: Forecasting Methodology
deprecated: false
hidden: true
metadata:
  robots: index
---
## Forecasting Methodology

Our forecasting methodology leverages a **multi-model approach**, incorporating insights from **Marketing Mix Modeling (MMM)** to enhance accuracy. The forecast is adjusted based on **incrementality insights from MMM** and accounts for **diminishing returns** in ad spend.

We approach the forecasting problem as a combination of two key questions:

1. **How much of the KPI can be expected?**
2. **How should the budget be allocated to achieve that KPI?**

<br />

1. The KPI is modeled as a function of both paid and non-paid components:

<br />

```
     $$ KPI = f(P_{\text{paid}}) + f(N_{\text{transformed}}) + f(N_{\text{raw}}) $$
```

<br />

```
```

<br />

```
```

### Understanding Channel Saturation in Measurement Models

<br />

While the concept of saturation is straightforward—additional spending does not always result in higher **marginal reach**—its implementation in modeling presents challenges.

<br />

Most measurement models focus on **outcome metrics** (e.g., **D2C revenue, new orders**) rather than **reach**. The key question is:\
**Does increased spending always result in lower marginal outcomes?**

<br />

The answer is nuanced. Even though modeling assumes **smooth, curve-based transformations** for saturation, real-world outcomes can be less predictable.

<br />

For example, you may have been investing in **Facebook prospecting** since January and observed diminishing returns for the first few months. Then, suddenly, there's a spike in returns. This could be due to:

* Changes in messaging
  * Introduction of new creative formats
    * External factors like seasonality or platform algorithm changes
      <br />
      Even if a channel appears saturated in terms of **reach**, incremental outcomes can still experience fluctuations.
      <br />

### The S-Curve vs. C-Curve Considerations

<br />

Many models assume that channels follow an **S-curve** pattern of diminishing returns. However, a critical limitation arises:

* When building models, we typically use data from the last **2-3 years**.
  * However, the channel itself may have been operating **for much longer**.
    * By the time modeling begins, the channel might have **already moved beyond the S-curve** into a **C-curve** phase.
      <br />
      Thus, models should not assume that a channel is still in the early **S-curve** phase—it may have already reached **maturity or decline**.
      <br />

### Selecting a Base Period for Saturation Analysis

<br />

To address these challenges, we help users **choose a base period**—a specific **month or quarter** that best represents the **current state of the business**.

<br />

Based on this **reference period**, we assess the saturation of each channel. This ensures that:

* The model reflects **recent business conditions**, rather than outdated assumptions.
  * Adjustments to saturation are made **relative to the business's current phase**, rather than applying a one-size-fits-all approach.

<br />

By integrating these insights, our forecasting methodology provides **realistic and actionable** guidance for budget allocation and performance prediction.

## Key Components

### Multi-Model Approach

* We utilize multiple statistical and machine learning models to improve robustness and reduce bias.
* These models are ensembled to generate more reliable forecasts.

### Incrementality Adjustment from MMM

* The forecast is calibrated using MMM-derived incrementality factors.
* This ensures that the forecast reflects the true incremental impact of marketing investments rather than mere correlation.

### Diminishing Returns Consideration

* MMM insights help model the nonlinear response of marketing spend.
* Forecasts are adjusted to reflect saturation effects, preventing overestimation of returns at higher spend levels.

## Benefits

* **More Accurate Forecasts**: By integrating multiple models and MMM insights, our forecasts are more data-driven and reliable.
* **Realistic Budget Planning**: Adjustments for incrementality and diminishing returns help prevent over- or under-investment.
* **Actionable Insights**: Businesses can make informed decisions about future marketing strategies based on scientifically grounded forecasts.

## Use Cases

* Budget allocation and planning
* Performance forecasting for marketing campaigns
* ROI estimation with a data-driven approach

## Contact

For further details or to integrate this forecasting methodology into your workflow, please contact our analytics team.