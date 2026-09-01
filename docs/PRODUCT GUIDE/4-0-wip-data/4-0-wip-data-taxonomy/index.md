---
title: '[4.0][WIP] Data Taxonomy'
excerpt: >-
  Group your campaigns into tactics so that measurement reflects how your
  marketing actually works, not how your campaigns happen to be named.
hidden: true
---
Ad platforms organise spend the way the platform wants to organise it: by account, campaign, ad set, ad. That structure is useful for running campaigns and close to useless for measuring them, because two campaigns sitting next to each other in the same account can be doing completely different jobs.

Consider a Google Ads account with a campaign defending your brand terms and another prospecting on generic keywords. The brand campaign will show a wonderful return, because people searching your name were mostly going to buy anyway. The prospecting campaign will look worse and may be the one genuinely growing the business. Average them into a single Google Ads number and you have hidden the only insight that mattered.

Data Taxonomy is where you fix that. You group campaigns into **tactics**, which are the units you actually want to measure.

![The Tactic mapper, showing campaigns waiting to be assigned a tactic](https://files.readme.io/40c936dd49cf910b84fef6342458da83dd6e4252ceb1fd7cf5a35da5aac9c922-taxonomy-mapper.png)

## What a tactic is

A tactic is a marketing job, described in your own words. It usually combines a channel with an intent, and often a funnel position:

- Paid Search Brand Upper
- Paid Search Non-Brand Lower
- Paid Social Prospecting Upper
- Paid Social Retargeting Lower
- Online Video Awareness Upper
- Shopping Performance Lower

There is no correct list. The right set is the one that matches the decisions you make. A good rule of thumb: **create a tactic when you would plausibly change its budget independently of everything else.**

## Getting around the tab

Two sub-tabs sit at the top. **Tactic mapper** is the working surface where campaigns get assigned. **Rules and labels** is where the automatic assignment rules live.

Inside the mapper you can switch between **Campaigns** and **Ad Sets**. Campaign level is where most people work. Drop to ad set level when one campaign genuinely contains several tactics, which happens most often on Meta.

### How campaigns and ad sets relate

This is worth understanding properly, because it is the source of the most commonly missed problem in the whole tab.

**The ad set is the atomic unit.** A tactic is really assigned to ad sets. A campaign owns several ad sets, and nothing forces them all onto the same tactic. What the Campaigns view shows you is therefore a roll-up of what its ad sets say.

That gives a campaign five possible states.

| State | What it means |
| --- | --- |
| **Unmapped** | None of its ad sets have a tactic. |
| **Fully mapped** | Every ad set is mapped, all to the same tactic. The quiet common case. |
| **Fully mapped, split** | Every ad set is mapped, but across two or more tactics. Perfectly valid. |
| **Partially mapped** | Some ad sets are mapped and some are not, all to one tactic. |
| **Partially mapped, split** | Some ad sets are mapped and some are not, across several tactics. |

**The two partial states are the ones to hunt for.** A campaign with four of its five ad sets mapped looks broadly fine at a glance, and the spend in that fifth ad set silently never reaches the model. It is not reported as an error anywhere, because nothing has gone wrong technically. It is simply unclassified.

Because the mapper states these separately, you can filter on them. Open the Tactic column's status filter and look for the partial states specifically. Doing that once a month catches the campaigns that grew a new ad set since you last looked.

The Tactic cell on a partially mapped campaign also shows the breakdown, so you can see how many of its ad sets are mapped, to which tactics, and how much spend is sitting unmapped underneath.

### The columns

| Column | What it tells you |
| --- | --- |
| **Name** | The campaign name as the platform reports it, with its ID underneath. |
| **Tactic** | What this campaign has been classified as. Starts as Not Assigned. |
| **Channel** | Which platform the spend came from. |
| **Account Name** | Which ad account it sits in. |
| **Objective** | The platform's own objective, such as SEARCH. Often a good hint when you are unsure. |
| **Spend** | How much this campaign spent over the period. |
| **Spend Share** | That spend as a share of the total, so you can see what is worth your attention. |
| **New** | Flags campaigns that have appeared recently and are not classified yet. |

**Columns** shows or hides columns, including custom dimensions from Data Transformation. The download icon exports the current view as CSV, useful when you want to agree tactics with a colleague in a spreadsheet first.

### The progress bar

Along the bottom is an honest summary: how much spend is mapped, how many campaigns and ad sets are unmapped, and how many tactics exist.

Watch the **spend mapped** percentage rather than the campaign count. Classifying 80 percent of campaigns means little if they are the ones spending nothing. Getting 95 percent of spend mapped is real progress.

## Two ways to assign tactics

Most teams use both.

| Use case | Approach | Read more |
| --- | --- | --- |
| First pass, exceptions, and the long tail | Select campaigns and assign them directly | [Assign tactics by hand](https://docs.lifesight.io/docs/4-0-wip-assign-tactics-manually) |
| Anything that repeats, and campaigns that do not exist yet | Write a rule that matches a pattern | [Assign tactics automatically with rules](https://docs.lifesight.io/docs/4-0-wip-assign-tactics-rules) |

Start by hand to learn what patterns exist, then write rules so the taxonomy maintains itself.

## Getting good results

**Lean on your naming convention, and fix it if you cannot.** Rules work well when names follow a pattern. If yours do not, this tab will show you that clearly, and the long term fix is a convention rather than more rules.

**Start coarse.** Half a dozen tactics everyone understands beats thirty nobody maintains.

**Do it with the person who runs the campaigns.** They know which campaigns were experiments and which are dormant. That context is not in the data.

**Come back monthly.** Sort by the New column and classify what has appeared.

**Do not classify what does not matter.** Campaigns with negligible spend can stay unassigned without harming a model.

## Common questions

**What happens to campaigns I never classify?**
They stay unassigned. Their spend is recorded, but they cannot be measured as part of a tactic.

**Can a campaign belong to two tactics?**
No. If it is genuinely doing two jobs, split it at ad set level.

**I renamed a campaign. Do I lose its tactic?**
No. Assignments follow the campaign ID rather than its name.

**Does this change my campaigns?**
No. Nothing here writes back to the ad platform.

**Where do tactics get used?**
Mainly in [Model Schema](https://docs.lifesight.io/docs/4-0-wip-model-schema), where paid media variables are defined by channel and tactic, and in reporting where you want performance grouped the way you run marketing.