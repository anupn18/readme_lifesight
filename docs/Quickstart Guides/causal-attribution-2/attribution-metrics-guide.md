---
title: Attribution metrics guide
excerpt: >-
  Know what every Attribution metric measures, how it's calculated, and which
  one to lead with for each budget decision.  #
deprecated: false
hidden: false
metadata:
  title: Attribution metrics guide
  robots: noindex
---
Attribution in Lifesight gives you every number you need to judge your marketing in one place, from what platforms report to what your spend actually caused and whether it's on plan. It combines four groups of metrics: incremental performance, platform-reported performance, spend and pacing, and recommendations.&#x20;

![](https://files.readme.io/939dca0956ecea5a948e89b34f5255d9e7060f0ad346b3447dd1db1e65f6370d-Screenshot_2026-09-22_at_12.35.35_PM.png)

## Measure what your marketing caused

Incremental metrics show the revenue and conversions your advertising actually drove, beyond what would have happened anyway. These are the metrics to lead with when deciding where to invest.

| Metric                  | Definition                                                     | Formula                                                  | When to lead with it                                               |
| ----------------------- | -------------------------------------------------------------- | -------------------------------------------------------- | ------------------------------------------------------------------ |
| Incremental Revenue     | Revenue estimated to be causally driven by advertising         | Provided by Lifesight measurement                        | Reporting the real revenue impact of your marketing                |
| iROAS                   | Incremental return for each unit of spend                      | Incremental Revenue / Actual Spend                       | Comparing true efficiency across channels, campaigns, or ad sets   |
| Incremental Conversions | Conversions estimated to be causally driven by advertising     | Platform Conversions adjusted by incrementality evidence | Measuring impact when your goal is conversions rather than revenue |
| iCPA                    | Cost per incremental conversion                                | Actual Spend / Incremental Conversions                   | Judging acquisition efficiency for conversion-focused campaigns    |
| Incrementality Factor   | Share of platform-reported revenue estimated to be incremental | Incremental Revenue / Platform Revenue                   | Spotting channels that claim more credit than they earn            |
| Marginal ROAS           | Incremental revenue expected from the next unit of spend       | Derived from the promoted model                          | Deciding where to put new budget                                   |

**How to read them together**

- **iROAS versus Marginal ROAS:** iROAS is the average return across all spend to date. Marginal ROAS is the return on the next dollar. A campaign with a strong iROAS but a falling Marginal ROAS has likely saturated, so extra spend won't return at the same rate.
- **Incrementality Factor:** a factor of 0.4 means Lifesight estimates about 40% of what the platform reports for that row and period is incremental. The rest is likely demand that was already coming.

## Compare with what platforms report

Platform-reported metrics show performance as each advertising platform records it. They're useful for delivery and volume, but they include conversions that would have happened without the ad. Read them alongside incremental metrics to see how much reported performance holds up.

| Metric               | Definition                                       | Formula                             | When to lead with it                                             |
| -------------------- | ------------------------------------------------ | ----------------------------------- | ---------------------------------------------------------------- |
| Platform Revenue     | Revenue reported by the advertising platform     | Platform value                      | Reconciling Lifesight results with platform dashboards           |
| Platform ROAS        | Platform-reported return on spend                | Platform Revenue / Actual Spend     | Showing the gap between reported and incremental return          |
| Platform Conversions | Conversions reported by the advertising platform | Platform value                      | Checking conversion volume as the platform records it            |
| Platform CPA         | Platform-reported cost per conversion            | Actual Spend / Platform Conversions | Comparing with iCPA to see how much reported efficiency holds up |
| Impressions          | Number of ad impressions served                  | Platform value                      | Confirming delivery and reach                                    |
| Clicks               | Number of ad clicks recorded                     | Platform value                      | Checking engagement and traffic volume                           |

**Why Platform ROAS is usually higher than iROAS**

Platforms credit their ads for every conversion that follows an exposure, including ones that would have happened anyway. iROAS counts only the revenue your spend actually created, so the distance between the two shows how much credit platforms are claiming for conversions they didn't cause.

**Why the numbers differ**

Beyond conversions that would have happened anyway, four more things push platform-reported numbers away from incremental ones.

* **The same conversion claimed by several platforms:** a customer sees a Meta ad, later clicks a Google ad, then converts. Both platforms report it, so platform totals add up to more than you actually sold.
* **Attribution windows:** platforms keep counting conversions for days after a click or a view, whether or not the ad drove them.
* **Conversions the platform can't see:** sales that happen offline or through other channels never reach the platform, so its numbers miss them.
* **Effects that arrive later:** awareness ads often lead to conversions weeks later, or through search and direct visits, outside the platform's window.

**What to expect by funnel stage**

The closer an ad sits to the purchase, the more platforms tend to over-credit it. The further away it sits, the more they under-credit it. How big the gap gets depends on your brand, market and account setup.

| Funnel stage | Typical channels | Platform vs incremental | Why |
| --- | --- | --- | --- |
| Lower funnel | Brand search, retargeting | Platform usually higher | Most of the people reached were already close to buying |
| Mid funnel | Non-brand search, prospecting with a conversion goal, shopping | Closer, can go either way | People are still shopping around, so more of the reported conversions are new |
| Upper funnel | Video, YouTube, CTV, display, audio | Platform can be lower | Few people click, and conversions come later through search or direct visits |
| Offline | TV, print, OOH, events, PR | Platform reports nothing | Measure these with your model or a geo experiment |

**What to expect by platform**

These are each platform's default windows. Most can be changed in the ad account, so compare at the window the account actually uses.

| Platform | Default window | What it means |
| --- | --- | --- |
| Meta | 7-day click, 1-day view | Retargeting and view credit push numbers up |
| Google Search | 30-day click | Brand terms look best in the platform but add the least. Non-brand holds up better |
| YouTube | 3-day engaged view (web conversions) | Usually under-reported. Much of video's effect shows up later in search and direct visits |
| LinkedIn | 30-day click, 7-day view | Long sales cycles and view credit can move it either way |
| TikTok | 7-day click, 1-day view | Similar to Meta |

**Example**

In a large field experiment, eBay switched off its brand-keyword search ads. Sales barely moved in the short term, because shoppers clicked the organic listing instead. The ads had been getting credit for sales that would have happened anyway. This is why brand search often shows a high Platform ROAS and a low Incrementality Factor.

## Track spend against your plan

Spend and pacing metrics compare what you've spent with what your active scenario (the media plan you've selected as your benchmark) planned. Use them to catch overspend and underspend before the period closes.

| Metric                | Definition                                            | Formula                                         | When to lead with it                                           |
| --------------------- | ----------------------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------- |
| Actual Spend          | Spend recorded during the selected period             | Platform value                                  | Confirming how much you've invested                            |
| Planned Spend         | Budget allocated by the active scenario               | Scenario value                                  | Checking what the plan expected you to spend                   |
| Pacing                | Actual spend relative to planned spend to date        | Actual Spend / Planned Spend to Date            | Seeing at a glance whether you're on, ahead of, or behind plan |
| Total Delta           | Cumulative difference from plan                       | Actual Spend minus Planned Spend                | Sizing how far off plan you are in total                       |
| Daily Average Spend   | Average spend per elapsed day                         | Actual Spend / Days Elapsed                     | Understanding your current daily run rate                      |
| Daily Average Planned | Expected daily rate to date                           | Planned Spend to Date / Days Elapsed            | Comparing your run rate with the planned rate                  |
| Daily Gap             | Difference between actual and planned daily rates     | Daily Average Spend minus Daily Average Planned | Pinpointing how much daily spend needs to change               |
| Recommended Daily     | Catch-up adjusted daily spend for the next seven days | Remaining Budget / Remaining Days               | Setting a concrete daily budget in the platform                |

**Example**

If a campaign's Planned Spend to date is $10,000 and its Actual Spend is $8,000, its Pacing is 80% and its Total Delta is -$2,000. Recommended Daily spreads the remaining budget across the remaining days, so the gap closes gradually rather than through a sudden spike in spend.

## Know which way to move spend

Recommendations translate pacing into a suggested direction for each channel, campaign, or ad set.

- **Scale:** under-pacing against the active plan.
- **Maintain:** pacing within the expected range.
- **Reduce:** over-pacing against the active plan.

Recommendations are based on pacing, so read them alongside incremental metrics before acting. A **Scale** flag on a campaign with a low Incrementality Factor may mean the budget would do more elsewhere.

## Find the metrics you need

Metric availability depends on the connected platforms, promoted measurement assets, and selected reporting range. Columns with no received data or only zero values may be hidden automatically and can be revealed from the table controls using **Choose columns**.

***

## Frequently Asked Questions

**Which metric should I use to compare channel efficiency?**
Use iROAS. It shows the incremental return for each unit of spend, so you're comparing what each channel actually caused rather than what it reported.

**What is the difference between iROAS and Platform ROAS?**
Platform ROAS uses revenue reported by the advertising platform. iROAS uses incremental revenue, which counts only the revenue your advertising actually drove. Platform ROAS is usually higher.

**What is the difference between iROAS and Marginal ROAS?**
iROAS is the average incremental return across all spend to date. Marginal ROAS is the incremental revenue expected from the next unit of spend, derived from your promoted model.

**How is the Incrementality Factor calculated?**<br />Incremental Revenue divided by Platform Revenue. It shows the share of platform-reported revenue estimated to be incremental.

**Can the Incrementality Factor be above 1?**<br />Yes, though it's less common. It means Lifesight estimates the ads are driving more than the platform can see, which tends to happen on video and other upper-funnel channels whose conversions arrive later or through other channels.

**Should I switch off a channel with a low Incrementality Factor?**<br />Not necessarily. A low factor usually means the channel is harvesting existing demand, so rebalance spend rather than switching it off. Open the channel by tactic, campaign and ad set to see where the gap comes from, and move budget in steps rather than all at once.

**Will the gap between platform and incremental numbers stay the same?**<br />No. It changes with targeting, creative, seasonality and how saturated a channel is. Check it again after your model is retrained.

**How are Incremental Conversions calculated?**<br />Platform conversions are adjusted using incrementality evidence from your promoted measurement assets.

**When should I use iCPA instead of iROAS?**<br />Use iCPA when your goal is conversions rather than revenue. It shows the cost per incremental conversion.

**Why is iCPA higher than Platform CPA?**<br />Platform CPA divides spend by every conversion the platform credits, including ones that would have happened anyway. iCPA divides the same spend by estimated incremental conversions only, so it is usually higher.

**What does a Pacing value of 80% mean?**<br />You've spent 80% of what your active scenario planned to date, meaning you're running under plan.

**How is Recommended Daily spend calculated?**
Remaining Budget divided by Remaining Days. It gives you a catch-up adjusted daily spend for the next seven days.

**What do Scale, Maintain, and Reduce mean?**
Scale indicates under-pacing, Maintain indicates pacing within the expected range, and Reduce indicates over-pacing against the active plan.

**Why can't I see some metrics?**
Metric availability depends on your connected platforms, promoted measurement assets, and selected reporting range. Columns with no data or only zero values may be hidden automatically. Reveal them using **Choose columns**.

**Why don't I see Marginal ROAS?**
Marginal ROAS is derived from your promoted model. Make sure a Marketing Mix Model is promoted for your workspace.