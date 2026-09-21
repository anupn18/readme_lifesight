---
title: '[4.0][WIP]Breakdown: find exactly where performance is won or lost'
excerpt: >-
  Move from channels down to ad sets, compare planned spend with what actually
  worked, and act on the specific line items driving your results.
deprecated: false
hidden: true
metadata:
  title: >-
    Breakdown: Causal attribution across channels, tactics, campaigns, and ad
    sets
  description: >-
    See incremental performance at every level of your marketing hierarchy.
    Drill from channels into tactics, campaigns, and ad sets, compare actual
    spend against plan, and act on scale, maintain, or reduce recommendations.
  keywords:
    - causal attribution breakdown
    - incremental revenue by channel
    - campaign level incrementality
    - ad set performance
    - iROAS by campaign
    - marginal ROAS
    - incrementality factor
    - spend pacing by campaign
    - scale maintain reduce recommendations
    - weekly spend pacing
    - tactic level attribution
    - planned versus actual spend
  robots: noindex
---
Breakdown takes the performance picture from Overview and shows you exactly where it comes from. Instead of knowing that a channel is underperforming, you can see which tactic, which campaign, and which ad set is responsible, and what to do about each one.

![](https://files.readme.io/546fa2ea663fbba98e323f9895d8817ec055be9b003d12aae54d5bb1cfee2a77-Screenshot_2026-09-18_at_3.39.28_PM.png)

<br />

Every number here is causal, not platform-reported. That means you are ranking and cutting based on what each line item actually contributed, not on the conversions each platform claimed.

## Start broad, then narrow to the line item that matters

Breakdown follows your marketing hierarchy. Levels appear only when there is data behind them.

- Channels, the platforms you buy on
- Tactics (the role a group of spend plays, such as prospecting or retargeting)
- Campaigns
- Ad Sets<br />

  ![](https://files.readme.io/577aaed154e621c4879bb8920d5b840384dd0ea31a8b4e4b28142a4da2eff504-Screenshot_2026-09-18_at_3.40.39_PM.png)

Work top down. Select one or more rows at the level you are on, then choose Drill into to carry that selection forward and filter the next level to only what you selected. Clear the selection to return to the full level.

This is the fastest path from a symptom to a cause. A channel with a weak incrementality factor rarely fails evenly. Drilling in usually shows a small number of retargeting campaigns pulling the whole channel down while prospecting holds up.

## Shape the table around the question you are asking

Use **search** to jump straight to an entity by name or account when you already know what you are looking for.

Select **Choose columns** to show, hide, and reorder metrics. Columns with no data or only zero values can be hidden automatically, which keeps the table readable when a level has partial coverage.

Common columns include:

- **Recommendation and pacing**, for the action and the delivery status
- **Actual spend**, planned spend, and spend delta, for how far off plan the entity is
- **Impressions, clicks, and conversions**, for delivery volume
- **Platform revenue and incremental revenue**, side by side
- **Platform ROAS and iROAS&#x20;**(incremental return on ad spend, or incremental revenue divided by spend)
- **Marginal ROAS** (the return on the next dollar you add, rather than the average return across all spend to date)
- **Incrementality factor**, the share of platform-reported revenue estimated to be incremental
- **CPA** (cost per acquisition)

Marginal ROAS is the column to add when you are deciding where to put new budget. A campaign can hold a strong average iROAS while its marginal ROAS falls, which means it has saturated and extra spend will not return at the same rate.

## Act on a recommendation for every entity

Each row carries a recommendation based on how its actual spend compares with the active target scenario.

- Scale for entities running under plan
- Maintain for entities pacing near plan
- Reduce for entities running over plan

Read these against incremental performance rather than on their own. A Scale flag on a campaign with a low incrementality factor means it is under-delivering on a plan it probably should not have had, so the better move is to reallocate that budget rather than push the campaign back on track.

## Check the weekly view before you change spend

Select **Weekly** for any entity to open its week by week detail:

![](https://files.readme.io/f12648e0222a59d418ef650f091c4b856d29bc9f89bdb36c7fea8f644c95b985-Screenshot_2026-09-18_at_3.50.54_PM.png)

- **Planned and actual spend by week**, so you can see when the gap opened
- **Pacing, plus weekly delta&#x20;**&#x61;nd cumulative delta
- **Daily averages**

* **Recommended daily spend** for the next seven days

![](https://files.readme.io/dc9084de69d8b3c656e0b5c2dc26fc0bb46c7f320f7c7f95b995be88cfda746a-Screenshot_2026-09-18_at_3.44.22_PM.png)

<br />

This is where you separate a one-off week from a sustained trend.&#x20;

A campaign that is 20% under plan because of a single paused week needs a different response than one that has drifted under every week since launch. The recommended daily spend gives you a concrete number to take into the platform, sized to close the gap across the remainder of the scenario rather than all at once.

***

## Next up

Attribution metrics guide, for what each metric measures, how it is calculated, and when to lead with it.

<br />
