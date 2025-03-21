---
title: Forecasting Methodology
deprecated: false
hidden: true
metadata:
  robots: index
---
# Forecasting Approach

## Forecasting Methodology

Our forecasting methodology leverages a **multi-model approach**, incorporating insights from **Marketing Mix Modeling (MMM)** to enhance accuracy. The forecast is adjusted based on **incrementality insights from MMM** and accounts for **diminishing returns** in ad spend.

We approach the forecasting problem as a combination of two key questions:

1. **How much of the KPI can be expected?**
2. **How should the budget be allocated to achieve that KPI?**

The KPI is modeled as a function of both paid and non-paid components:

$$ &#x20;
KPI = f(P\_\{\text\{paid}}) + f(N\_\{\text\{transformed}}) + f(N\_\{\text\{raw}})
$$ &#x20;

This structure ensures that both **marketing investments (paid components)** and **external factors (non-paid components)** are appropriately accounted for, providing a holistic and data-driven approach to forecasting.

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