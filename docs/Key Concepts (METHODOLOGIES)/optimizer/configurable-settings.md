---
title: '[WIP] Configurable Settings'
deprecated: false
hidden: true
metadata:
  robots: index
---
The Optimizer works automatically, but you also have control over how it behaves. **Configurable settings** at the workspace level let you fine-tune the balance between caution and aggressiveness in budget recommendations.

These settings act as guardrails, shaping how recommendations are distributed and applied across campaigns.

### Allocation Weight

This setting determines how much emphasis the Optimizer places on:

* **Spend share** → Prioritizes campaigns with larger budgets.
* **Conversion share** → Prioritizes campaigns delivering more results.

By adjusting the allocation weight, you can control whether Optimizer leans more towards scaling **high-spend campaigns** or **high-performing campaigns**.

### Cap Percentage

To prevent sudden swings, you can set a **cap on weekly budget increases**.

* For example, a 20% cap ensures no campaign’s budget grows more than 20% per week, even if the recommendation is higher.
* This keeps changes manageable and avoids shocking campaigns out of their learning phase.

### Minimum Days Remaining

Campaigns with only a few days left in their schedule aren’t good candidates for scaling. This setting defines the **minimum number of days a campaign must have left** to be eligible for recommendations.

### Lifetime Spending Threshold

This setting ensures that campaigns close to exhausting their lifetime budgets don’t receive unnecessary increases. The Optimizer will automatically deprioritize campaigns that are nearly capped.

### Why These Settings Matter

These controls let you:

* **Balance risk vs growth** → Decide if you want Optimizer to behave more conservatively or aggressively.
* **Align with campaign realities** → Respect pacing, end dates, and caps.
* **Customize to your strategy** → Different teams may prefer different levels of automation, and these settings let you set the tone.

> 📘 _Tip:_ These settings apply **workspace-wide**. Once configured, all plans and scenarios in that workspace will follow the same guardrails.