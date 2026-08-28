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

## How new campaigns get assigned

This is the reason rules exist, so it is worth being precise about it.

A rule is not a one time bulk action. It is a standing instruction. The rules manager states it plainly at the top: rules automatically assign matching campaigns to a tactic, **now and as new campaigns arrive**.

So the sequence for a campaign launched next Tuesday is:

1. The campaign appears in Lifesight on the next sync from the ad platform.
2. Every rule is evaluated against it.
3. If one matches, the campaign is assigned that tactic immediately. Nobody has to do anything.
4. If several match, the one with the highest priority wins. See below.
5. If none match, it stays unassigned and shows up in the **New** column.

The **New** column flags campaigns and ad sets created in the last 30 days. That is your working list. Filter on it, see what your rules did not catch, and either assign those by hand or widen a rule.

Two things follow from this that are easy to miss.

**Rules apply retroactively too.** Writing a rule today classifies matching campaigns in your history as well as future ones, so you do not need a separate backfill.

**A campaign that stops matching does not keep its rule assignment.** If someone renames a campaign so it no longer matches, ownership falls through to the next rule that claims it, or to nobody. This is why a bulk rename in the ad platform is worth following with a check here.

## Rule priority

When two rules both match a campaign, something has to decide. That is priority.

### How priority works

Priority is a **position in an ordered list, not a label you type**. The list runs from 1 to N with no gaps, where **1 is the highest priority**.

The rule that matters: **when several rules claim the same campaign, the one with the lowest priority number wins.**

Priority runs top to bottom in the editor. The rule at the top has the highest priority and claims a campaign ahead of everything below it.

### How priority is set when you create a rule

A new rule is added to the list and takes its position there. Because the positions are always contiguous, inserting a rule at a given position pushes everything from that point down by one. You never end up with two rules at priority 3, and you never have to renumber by hand.

### How to change it

Open the priority editor from the rules manager. Rules are listed top to bottom in priority order, and you reorder them by dragging the grip handle on the left of each row. An insertion line shows where the dragged rule will land before you drop it.

You can also move a rule with the keyboard: focus its handle and use the up and down arrow keys, where up is higher priority.

Reordering one rule shifts the others, so the changes only make sense as a set and are applied together rather than one at a time.

### How to order them

**Most specific at the top, most general at the bottom.**

A rule for one product line should sit above the broad rule for its whole channel. If the broad rule sits higher, it claims everything first and the specific rule never gets a chance to run.

A worked example, in priority order:

1. Campaign Name contains `Brand` and Channel is Google, assign Paid Search Brand
2. Campaign Name contains `NB` and Channel is Google, assign Paid Search Non-Brand
3. Channel is Google, assign Paid Search Other

The third rule is a catch-all. It only ever picks up Google campaigns the first two did not claim, which is exactly what you want. Put it at the top instead and it would swallow everything.

### Exceptions

You can also exclude individual campaigns from a rule when the pattern is right but one campaign is genuinely an exception. Those exclusions survive re-evaluation, and the excluded campaign falls through to the next rule that claims it, or stays unassigned.

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
The one with the lowest priority number wins, meaning the one nearest the top of the list. Campaigns a rule explicitly excluded fall through to the next claimer, or stay unassigned.

**Do rules apply retroactively?**
Yes. A rule classifies matching campaigns in your history as well as new ones.

**I did a bulk rename in the ad platform. What breaks?**
Manual assignments survive, because they follow the campaign ID. Rules written against the old naming will stop matching, so check them after any bulk rename.

**Should I rule everything, or leave some manual?**
Both. Rules for the patterns, manual for the exceptions. Trying to express every exception as a rule produces a set nobody can reason about.

**Can I check a rule before committing to it?**
Yes, and you should. The preview lists every campaign the rule will claim before you save.
