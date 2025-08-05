---
title: Causality Flags
excerpt: >-
  Understand what determines whether a channel has a Casual relationship with
  the model
deprecated: false
hidden: true
metadata:
  robots: index
---
In a Marketing Mix Model, **causality** is the measure of confidence that a specific marketing channel is genuinely driving a business outcome. A truly causal model can accurately distinguish the impact of each individual channel, allowing you to understand its true return on investment (ROI).

### Why You Should Care About Causal Flags

Causal flags are your guide to the reliability of the model's findings for each channel. They tell you which channel insights you can trust implicitly and which ones require further action or investigation before you reallocate your budget.

> ℹ️ \*\*Use these flags to ensure you only invest marketing budget in channels that are proven to drive results for your business.

<br />

### Quick Reference Guide

| Symbol                                                                                                  | Causal Flag          | Meaning                                                                                                                                                                                                                                      | Primary Action                                                                                                        |
| :------------------------------------------------------------------------------------------------------ | :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------- |
| ![](https://files.readme.io/77f9c4b6b38f9d817a81a98d9149c11610de1d0d4524788a7a6007ff69e7c1f9-image.png) | **Is Causal**        | High confidence. The model can isolate the channel's impact.                                                                                                                                                                                 | **Trust these insights.** Use for budget allocation.                                                                  |
| ![](https://files.readme.io/1d843cb341825579ce279b7b906a306da0f77914dc6e06d4a8ed6c6bcf643944-image.png) | **Not Causal**       | The model struggles to find a reliable causal link. This can be due to: <ul><li>High correlation with another channel</li><li>Implausible iROAS/iCPA values</li><li>Not enough data points</li><li>Low variation in channel spends</li></ul> | **Improve data quality.** Vary spends, collect more data, or run a targeted experiment to establish a clearer signal. |
|                                                                                                         | **High Interaction** | The variable is too similar to your outcome KPI, causing distortion.                                                                                                                                                                         | **Re-classify or remove** the flagged variable from the model.                                                        |

<br />

### Understanding the Causal Flags in Lifesight

The platform displays one of three flags for each variable in your model.

#### ### Is Causal

This is the ideal state for a marketing channel in your model.

* **Criteria:** The model identifies a channel as causal when there is sufficient data variation and its correlation with other channels is low (specifically, a correlation value below 0.75).
* **What It Means:** When spending patterns between two channels are distinct, the model can clearly isolate the incremental contribution of each one. You can have high confidence in the ROI and response curve data for this channel.
* **Recommended Action:** Use the insights from these channels for budget optimization and forecasting.

#### ### Not Causal (High Correlation)

This flag indicates that the model cannot confidently distinguish a channel's unique impact.

* **Criteria:** This flag appears due to a few reasons like lower than necessary spends data for the channel, unreasonably high iROAS, inexplicably low iCPA, and lower than necessary variations in spends for the channel.
* **What It Means:** This often happens when channels behave similarly. For example, when you run a major TV campaign, you might see a simultaneous lift in both "Branded Search" and "Direct Website Traffic," making their spending patterns highly correlated. The model struggles to determine how much credit each channel should get individually.
* **Recommended Action:** An experiment is needed to establish causality.
  > ⚠️ \*\* To resolve this, you need to create the data variation the model is missing. Running a controlled experiment, like a geo-holdout test where you pause a specific channel in one region, can help the model learn the true incremental impact of that channel.

#### ### High Interaction Effect

This flag warns you that a variable may be distorting your results because it's closely related to your final outcome.

* **Explanation:** A high interaction effect occurs when an input variable (especially an organic one) is not an independent driver of your KPI, but is instead a direct part of, or a step towards, that same outcome. This can lead to the model "double-counting" the result and inflating the variable's importance.
* **Example:** Imagine your primary goal is `{{YOUR_KPI}}`, and you include "Adds to Cart" as an organic variable in the model. A customer must "Add to Cart" before they can generate revenue. In this case, "Adds to Cart" is a step *in the process* of achieving `{{YOUR_KPI}}`, not an independent marketing activity *causing* it. The model may flag this as a high interaction.
* **Recommended Actions:**
  * **Re-classify the Variable:** If the flagged variable is a crucial business metric that is part of the customer journey to your main KPI, consider marking it as a secondary outcome KPI in your model setup.
  * **Remove the Variable:** If the variable is redundant or incorrectly classified as a marketing driver, removing it from the model will prevent confusion and improve the accuracy of your core marketing insights.

### Best Practices for Ensuring Causality

* **Vary Your Spend:** When planning your marketing budget, intentionally create variations in spending across channels over time. This provides the model with clearer signals to learn from.
* **Design Experiments Proactively:** Don't wait for a "Not Causal" flag. Regularly run controlled experiments to validate the model's findings and uncover deeper insights into channel incrementality.
* **Review Your Inputs:** Before running a model, carefully consider if your input variables are true "causes" (marketing channels) or "effects" (steps in the conversion funnel).