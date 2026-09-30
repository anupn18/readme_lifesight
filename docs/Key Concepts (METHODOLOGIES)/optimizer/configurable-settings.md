---
title: Configurable Settings
excerpt: Workspace guardrails that shape how recommendations are generated and applied.
deprecated: false
hidden: true
metadata:
  robots: index
---
Recommendations are generated automatically, but you have control over how they behave. Configurable settings at the workspace level let you fine tune the balance between caution and aggressiveness.

These settings act as guardrails, shaping how recommendations are distributed and applied across campaigns.

## Allocation weight

This setting determines how much emphasis is placed on spend share, which prioritises campaigns with larger budgets, against conversion share, which prioritises campaigns delivering more results. Adjusting it controls whether recommendations lean toward scaling high spend campaigns or high performing ones.

## Cap percentage

To prevent sudden swings, you can cap weekly budget increases. A 20 percent cap ensures no campaign's budget grows more than 20 percent per week, even if the recommendation is higher. This keeps changes manageable and avoids shocking campaigns out of their learning phase.

## Minimum days remaining

Campaigns with only a few days left in their schedule are not good candidates for scaling. This setting defines the minimum number of days a campaign must have left to be eligible for a recommendation.

## Lifetime spending threshold

This ensures campaigns close to exhausting their lifetime budgets do not receive unnecessary increases. Campaigns that are nearly capped are deprioritised automatically.

## Why these settings matter

They let you balance risk against growth, deciding whether recommendations behave conservatively or aggressively. They keep recommendations aligned with campaign realities such as pacing, end dates and caps. And they let different teams set the level of automation that suits their strategy.

These settings apply workspace wide. Once configured, every plan in that workspace follows the same guardrails.

<br />
