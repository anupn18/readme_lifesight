---
title: '[WIP] Allocation Score'
deprecated: false
hidden: true
metadata:
  robots: index
---
Behind every recommendation in the Optimizer is an **allocation score**. This score determines how scenario-level budget adjustments are distributed fairly and logically across your campaigns and ad sets.

Think of it as the Optimizer’s way of answering:
👉 _“If I need to increase or decrease spend, which campaigns deserve a bigger share, and why?”_

### Why Allocation Scores Matter

* **Fair distribution**: Budget changes aren’t applied equally. Campaigns that drive more conversions or account for a larger share of spend receive proportionally larger adjustments.
* **Performance-driven**: Allocation scores balance two key signals:
  * How much you currently spend on a campaign
  * How many incremental conversions that campaign delivers
* **Smarter scaling**: This ensures that scaling focuses on campaigns with proven performance, rather than spreading budget thinly across underperformers.

### How Scores Are Calculated

Each campaign is assigned a score based on:

* **Spend share** → The percentage of spend this campaign represents within its tactic.
* **Conversion share** → The percentage of conversions this campaign contributes.
* **Workspace weight** → A configurable setting that balances the two.

By default, the system blends both signals, but your workspace settings control whether **spend** or **conversions** have more influence.

> 📘 _Example:_
>
> * If Campaign A contributes 60% of conversions in a tactic, while Campaign B contributes only 10%, Campaign A will naturally receive a larger share of any budget increase.

### What You’ll See in the Optimizer

You won’t see allocation scores directly in the table. Instead, you’ll see the **outcome of the score** reflected in the recommended budget values:

* High-scoring campaigns → Larger “Scale Budget” recommendations
* Low-scoring or inactive campaigns → Smaller or “Maintain Budget” recommendations
* Ineligible campaigns (e.g., no spend or conversions) → No recommendations

This way, you can trust that recommendations are **data-driven and proportional**, without needing to interpret raw scores yourself.

### Why This Matters

* Budget changes aren’t arbitrary, they’re grounded in past performance helping you **trust the system**
* Ensures **efficient scaling**: Stronger campaigns get more fuel.
* Provides **transparency**: Even though the score itself isn’t shown, you know what factors drive the recommendations.