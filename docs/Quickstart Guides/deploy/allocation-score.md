---
title: Allocation Score
excerpt: >-
  How the causal engine decides which campaigns get a bigger share of a budget
  change.
deprecated: false
hidden: true
metadata:
  robots: index
---
Allocation scores make sure every budget change in Deploy lands where it will do the most good, so your strongest campaigns get more of any increase. Behind every recommendation in Deploy is an allocation score, calculated by the causal engine. This score decides how plan-level budget changes are shared across your campaigns and ad sets, fairly and logically.

Think of it as the engine's way of answering one question: if spend needs to go up or down, which campaigns deserve a bigger share, and why?

## Why allocation scores matter

* **Fair distribution:** budget changes are not split equally. Campaigns that drive more conversions or account for a larger share of spend get proportionally larger adjustments.
* **Performance-driven:** allocation scores balance two signals: how much you currently spend on a campaign, and how many incremental conversions that campaign delivers.
* **Smarter scaling:** scaling focuses on campaigns with proven performance, instead of spreading budget thinly across underperformers.

## How scores are calculated

Each campaign gets a score based on three inputs:

* **Spend share:** the percentage of spend this campaign represents within its tactic (the role a group of campaigns plays, such as prospecting or retargeting).
* **Conversion share:** the percentage of conversions this campaign contributes.
* **Workspace weight:** a configurable setting that balances the two.

By default, the system blends both signals. Your workspace settings control whether spend or conversions have more influence.

**Example**

Campaign A contributes 60% of conversions in a tactic. Campaign B contributes only 10%. When the plan calls for a budget increase, Campaign A receives a larger share of it.

## What you see in Deploy

Allocation scores are not shown in the table. You see their effect in the recommended budget values:

* High-scoring campaigns get larger Scale recommendations.
* Low-scoring or inactive campaigns get smaller recommendations, or Maintain.
* Ineligible campaigns, for example those with no spend or conversions, get no recommendation at all.

The result: budget changes are based on past performance, not applied at random. Stronger campaigns get more fuel. Even though the score itself is hidden, you know which factors drive each recommendation.

## Frequently Asked Questions<br />

**What is an allocation score?**

It is a score the causal engine gives each campaign. It decides how much of a plan-level budget change each campaign receives.

**Why don't all campaigns get the same budget change?**

Equal changes would push budget into weaker campaigns. Allocation scores give larger adjustments to campaigns that drive more conversions or carry a larger share of spend.

**What goes into an allocation score?**

Three inputs: spend share within the tactic, conversion share within the tactic, and a workspace weight that balances the two.

**Are conversions in the score incremental?**

Yes. The score uses the incremental conversions each campaign delivers, not platform-reported conversions.

**Can I control whether spend or conversions matter more?**

Yes. The workspace weight is configurable in your workspace settings. By default, the system blends both signals.

**Are campaigns compared across the whole account or within a tactic?**

Within a tactic. Spend share and conversion share are calculated against the other campaigns in the same tactic.

**Can I see a campaign's allocation score?**

No. Scores are not shown in the Deploy table. You see their effect in the recommended budget values.

**Why did a campaign get a much larger Scale recommendation than others?**

It has a higher allocation score, usually because it contributes a larger share of conversions or spend within its tactic.

**Why did a campaign get Maintain or a small recommendation?**

It has a low score, or it is inactive. Low-scoring campaigns receive a smaller share of any budget change.

**Why does a campaign have no recommendation?**

It is ineligible, for example because it has no spend or conversions. Ineligible campaigns do not receive a score or a recommendation.

**Does a high score always mean a budget increase?**

No. The score decides each campaign's share of a change. If the plan calls for a decrease, the score shapes how that reduction is shared too.
