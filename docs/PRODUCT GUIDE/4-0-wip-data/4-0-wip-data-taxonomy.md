---
title: '[4.0][WIP] Data Taxonomy'
excerpt: >-
  Group your campaigns into tactics so that measurement reflects how your
  marketing actually works, not how your campaigns happen to be named.
hidden: false
---

# Data Taxonomy

Ad platforms organise spend the way the platform wants to organise it: by account, campaign, ad set, ad. That structure is useful for running campaigns and close to useless for measuring them, because two campaigns sitting next to each other in the same account can be doing completely different jobs.

Consider a Google Ads account with a campaign defending your brand terms and another prospecting on generic keywords. The brand campaign will show a wonderful return, because people searching your name were mostly going to buy anyway. The prospecting campaign will look worse and may be the one genuinely growing the business. Average them into a single Google Ads number and you have hidden the only insight that mattered.

Data Taxonomy is where you fix that. You group campaigns into **tactics**, which are the units you actually want to measure.

![The Tactic mapper, showing campaigns waiting to be assigned a tactic](https://files.readme.io/40c936dd49cf910b84fef6342458da83dd6e4252ceb1fd7cf5a35da5aac9c922-taxonomy-mapper.png)

## What a tactic is

A tactic is a marketing job, described in your own words. It usually combines a channel with an intent, and often a funnel position. Some examples:

- Paid Search Brand Upper
- Paid Search Non-Brand Lower
- Paid Social Prospecting Upper
- Paid Social Retargeting Lower
- Online Video Awareness Upper
- Shopping Performance Lower

There is no correct list. The right set of tactics is the one that matches the decisions you make. If you never move budget between brand and non-brand search, splitting them buys you nothing. If you argue about it every quarter, split them.

A good rule of thumb: create a tactic when you would plausibly change its budget independently of everything else.

## Getting around the tab

Two sub-tabs sit at the top.

**Tactic mapper** is the working surface, where campaigns get assigned.

**Rules and labels** is where the automatic assignment rules live.

Inside the mapper you can switch between **Campaigns** and **Ad Sets**. Campaign level is where most people work. Drop to ad set level when one campaign genuinely contains several tactics, which happens most often on Meta where prospecting and retargeting audiences share a campaign. Tactics are assigned from the Campaigns view, and the ad set view inherits from it unless you deliberately override.

### The columns

| Column | What it tells you |
| --- | --- |
| **Name** | The campaign name as the platform reports it, with its ID underneath. |
| **Tactic** | What this campaign has been classified as. Starts as Not Assigned. |
| **Channel** | Which platform the spend came from. |
| **Account Name** | Which ad account it sits in. Useful when the same campaign name exists in several accounts. |
| **Objective** | The platform's own objective, such as SEARCH or SEARCH_PARTNERS. Often a good hint when you are unsure. |
| **Spend** | How much this campaign spent over the period. |
| **Spend Share** | That spend as a share of the total, so you can see what is worth your attention. |
| **New** | Flags campaigns that have appeared recently and have not been classified yet. |

Use **Columns** to show or hide columns, including any custom dimensions you created in Data Transformation. The download icon exports the current view as CSV, which is handy when you want to agree tactics with a colleague in a spreadsheet before committing to them.

### The progress bar

Along the bottom you get an honest summary: how much spend has been mapped, how many campaigns and ad sets are still unmapped, and how many tactics exist. Watch the **spend mapped** percentage rather than the campaign count. Classifying 80 percent of campaigns means little if they are the ones spending nothing. Getting 95 percent of spend mapped is real progress.

## Assigning tactics by hand

Good for a first pass and for the awkward long tail.

1. Sort by **Spend** so the campaigns that matter are at the top.
2. Tick the campaigns that belong to the same tactic. You can select several at once.
3. Assign the tactic to the whole selection.
4. Save your changes.

Working top down by spend means the first ten minutes cover most of your budget.

## Assigning tactics with rules

Hand assignment does not survive contact with reality, because new campaigns launch every week and each one arrives unclassified. Rules solve that. A rule watches for a pattern and assigns a tactic automatically, including to campaigns that do not exist yet.

Open **Manage rules** to create one.

A rule is built from conditions. Each condition picks a dimension (campaign name, channel, objective, account, or any custom dimension you created), an operator, and a value. Operators cover the obvious cases: equals, contains, starts with, is in a list, is empty, and comparisons for numbers and dates.

A worked rule: *where Campaign Name contains `NB` and Channel is Google, assign Paid Search Non-Brand*.

Before you save, the rule previews exactly which campaigns it will claim. Read that list. It is the fastest way to discover that your `NB` convention was used for something else entirely in 2023.

### When two rules both match

Rules have a **precedence**, where 1 is highest. If several rules claim the same campaign, the lowest number wins. Order your rules from most specific to most general, so that a narrow rule for one product line is not overruled by a broad rule for the whole channel.

You can also exclude individual campaigns from a rule's preview when the pattern is right but a particular campaign is an exception. Those exclusions stick.

## Getting good results

**Lean on your naming convention, and fix it if you cannot.** Rules work well when campaign names follow a pattern. If yours do not, this tab will show you that clearly, and the long term fix is a naming convention rather than more rules.

**Start coarse.** Half a dozen tactics that everyone understands beats thirty that nobody maintains. You can always split a tactic later.

**Do it with the person who runs the campaigns.** They know which campaigns were experiments, which were renamed mid flight, and which are dormant. That context is not in the data.

**Come back monthly.** Sort by the New column, classify what has appeared, and you are done in a few minutes. Left for a quarter it becomes a chore.

**Do not classify what does not matter.** Campaigns with negligible spend can stay unassigned without harming a model.

## Common questions

**What happens to campaigns I never classify?**
They stay unassigned. Their spend is still recorded, but they cannot be measured as part of a tactic, so a model cannot separate their effect.

**Can a campaign belong to two tactics?**
No, one tactic per campaign. If a campaign is genuinely doing two jobs, split it at ad set level instead.

**I renamed a campaign in the platform. Do I lose its tactic?**
Assignments follow the campaign ID rather than its name, so renaming is safe. A rule written against the old name will stop matching, which is worth checking after a bulk rename.

**Does this change my campaigns?**
No. Nothing here writes back to the ad platform. Tactics are Lifesight's own grouping.

**Where do tactics get used?**
Mainly in [Model Schema](https://docs.lifesight.io/docs/4-0-wip-model-schema), where paid media variables are defined by channel and tactic, and in reporting where you want performance grouped the way you run marketing.
