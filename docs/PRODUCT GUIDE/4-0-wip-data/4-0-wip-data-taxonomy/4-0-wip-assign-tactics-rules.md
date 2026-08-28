---
title: '[4.0][WIP] Assign tactics automatically with rules'
excerpt: >-
  Write rules that classify campaigns by pattern, including campaigns that do
  not exist yet, so your taxonomy maintains itself.
hidden: false
---
Hand assignment does not survive contact with reality. New campaigns launch every week and each one arrives unclassified, so a taxonomy maintained purely by hand is out of date within a month.

A rule watches for a pattern and assigns a tactic automatically. Crucially it applies to campaigns that do not exist yet, so tomorrow's launches are classified the moment they appear.

## When to use it

- **Your campaign names follow a convention**, even a loose one
- **You have more than a handful of campaigns**, where clicking through them is not sustainable
- **New campaigns launch regularly** and you do not want to revisit this every week
- **Several accounts share a convention**, so one rule covers all of them

Use [Assign tactics by hand](https://docs.lifesight.io/docs/4-0-wip-assign-tactics-manually) for exceptions and for the long tail that no pattern describes.

## How to do it

1. Go to **Data > Data Taxonomy**.
2. Click **Manage rules**.
3. Create a rule and build its conditions.

A condition picks a dimension, an operator, and a value. The dimensions available include campaign name, channel, objective and account, plus any custom dimensions you created in [Data Transformation](https://docs.lifesight.io/docs/4-0-wip-data-transformation). Operators cover equals, contains, starts with, is in a list, is empty, and comparisons for numbers and dates.

A worked rule: *where Campaign Name contains `NB` and Channel is Google, assign Paid Search Non-Brand*.

4. **Read the preview before saving.** The rule shows exactly which campaigns it will claim. This is the fastest way to discover that your `NB` convention meant something entirely different in 2023.
5. Save the rule.

## Ordering rules by precedence

Rules have a precedence, where 1 is highest. When several rules claim the same campaign, the lowest number wins.

Order from most specific to most general, so a narrow rule for one product line is not overruled by a broad rule covering the whole channel.

You can also exclude individual campaigns from a rule's preview when the pattern is right but one campaign is an exception. Those exclusions stick.

## When your names are not consistent

Rules work well when campaign names follow a pattern. If yours do not, this tab will show you that very clearly, and no amount of clever rule writing fixes it properly.

The real fix is a naming convention going forward, agreed with whoever launches the campaigns. In the meantime, cover the big spenders by hand and write rules for whatever subset is consistent.

## Where this shows up in the rest of Lifesight

Rules matter more than manual assignment over time, because they determine whether your measurement stays correct without anyone tending it.

**Model Schema** and **Marketing Mix Modeling** read tactics as their paid media variables. When a new campaign launches and nothing classifies it, its spend sits outside every tactic. The model then has spend it cannot attribute to any variable, which quietly distorts the contributions it reports for the channels that were classified.

**Model Refresh** is where this bites hardest. A model that refreshes on a schedule will keep running against a taxonomy that is slowly going stale. Rules are what keep a refreshed model reading the same structure it was built on.

**Planner and Optimizer** generate plans and budget actions per tactic. Unclassified spend is invisible to both, so a plan can look balanced while a meaningful slice of budget is missing from it.

**Attribution** and **Analyze dashboards** group by tactic. Unclassified campaigns collect in an unassigned bucket, which is usually the first place someone notices that the taxonomy has drifted.

## Common questions

**What happens when two rules match the same campaign?**
The one with the lowest precedence number wins. Campaigns a rule explicitly excluded fall through to the next claimer, or stay unassigned.

**Do rules apply retroactively?**
Yes. A rule classifies matching campaigns in your history as well as new ones.

**I did a bulk rename in the ad platform. What breaks?**
Manual assignments survive, because they follow the campaign ID. Rules written against the old naming will stop matching, so check them after any bulk rename.

**Should I rule everything, or leave some manual?**
Both. Rules for the patterns, manual for the exceptions. Trying to express every exception as a rule produces a set nobody can reason about.

**Can I check a rule before committing to it?**
Yes, and you should. The preview lists every campaign the rule will claim before you save.
