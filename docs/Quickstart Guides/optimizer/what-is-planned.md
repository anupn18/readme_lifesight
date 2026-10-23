---
title: What is planned
excerpt: Work that is specified but not yet shipped in Deploy.
deprecated: false
hidden: true
metadata:
  robots: index
---
Deploy today covers budget and bid changes at campaign and ad set level. This page lists what is specified but not yet in the product, so you can tell the difference between a gap and a bug. Nothing here carries a date. Treat it as intent rather than commitment.

## Bid target recommendations

Bid targets can be viewed and changed today, but nothing recommends them. Opening the bid dialog in Recommended mode prints "no recommendation" against every entity, because no recommended bid value is produced anywhere in the pipeline. Planned: a recommended bid target alongside the recommended budget, offered through the same Recommended and Custom choice.

## Warnings

Warnings are designed but not yet produced. The apply dialogs always report no warnings on the selected entities. Planned: two kinds, neither of which blocks a change.

Caution, for a change that is large relative to the current budget, an increase that runs well ahead of recent delivery, or an entity sharing a budget pool with others that would move with it.

Informational, for a campaign near its end date, a lifetime budget with little runway left, or an entity too new for its delivery to have settled.

## Configurable settings

No setting is configurable today. Recommendations run on system defaults, and there is nothing in the product to change them. Four settings are planned, each applied workspace wide, so that once configured every plan in that workspace follows the same guardrails.

* Allocation weight. How much emphasis is placed on spend share, which prioritises campaigns with larger budgets, against conversion share, which prioritises campaigns delivering more results. It controls whether recommendations lean toward scaling high spend campaigns or high performing ones.
* Cap percentage. A ceiling on weekly budget increases. A 20 percent cap would mean no campaign's budget grows more than 20 percent in a week, even where the recommendation is higher, which keeps changes manageable and avoids shocking campaigns out of their learning phase.
* Minimum days remaining. The least number of days a campaign must have left in its schedule to be eligible for a recommendation, since a campaign about to end is a poor candidate for scaling.
* Lifetime spending threshold. Campaigns close to exhausting their lifetime budgets are deprioritised automatically, so they do not receive increases they cannot spend.

<br />

## Eligibility moving upstream

Today Causal Attribution generates recommendations for every entity mapped to a tactic, and Deploy filters down to what it can action, so the two can show different counts. Planned: eligibility applied once at generation, so anything Deploy shows is already deployable and the two always agree.

## Recommendation status

Deploy shows a status against each row today. Planned: remove it. A recommendation stays visible while the entity remains eligible, and deployment history lives in Logs only, because a budget is something you keep managing rather than a task you complete once.

## Tactic

The Tactic column exists but is not populated. Planned: fill it from the taxonomy mapping.

## Further tabs

Geo Targeting and Creative are planned alongside Budget & Bid. Geo Targeting covers market level changes, including applying and removing the exclusions a geo holdout experiment requires. Creative carries the Scale, Refresh, Maintain and Pause actions from the Creative module into the same apply and logging flow.

<br />
