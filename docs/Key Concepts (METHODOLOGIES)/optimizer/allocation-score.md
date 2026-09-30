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
Behind every recommendation in Deploy is an allocation score, calculated by the causal engine. This score determines how plan level budget adjustments are distributed fairly and logically across your campaigns and ad sets.

Think of it as the engine's way of answering: if I need to increase or decrease spend, which campaigns deserve a bigger share, and why?

## Why allocation scores matter

* Fair distribution: budget changes are not applied equally. Campaigns that drive more conversions or account for a larger share of spend receive proportionally larger adjustments.
* Performance driven: allocation scores balance two signals, how much you currently spend on a campaign and how many incremental conversions that campaign delivers.
* Smarter scaling: scaling focuses on campaigns with proven performance, rather than spreading budget thinly across underperformers.

## How scores are calculated

Each campaign is assigned a score based on:

* Spend share: the percentage of spend this campaign represents within its tactic.
* Conversion share: the percentage of conversions this campaign contributes.
* Workspace weight: a configurable setting that balances the two.

By default the system blends both signals, but your workspace settings control whether spend or conversions have more influence. If Campaign A contributes 60 percent of conversions in a tactic while Campaign B contributes only 10 percent, Campaign A receives a larger share of any budget increase.

## What you see in Deploy

Allocation scores are not shown in the table. You see the outcome of the score in the recommended budget values:

* High scoring campaigns receive larger Scale recommendations.
* Low scoring or inactive campaigns receive smaller recommendations, or Maintain.
* Ineligible campaigns, for example those with no spend or conversions, receive no recommendation at all.

Budget changes are grounded in past performance rather than applied arbitrarily, stronger campaigns get more fuel, and even though the score itself is not shown you know which factors drive the recommendation.

<br />
