---
title: Assign tactics automatically with rules
excerpt: >-
  Write rules that classify campaigns by pattern, including campaigns that do
  not exist yet, so your taxonomy maintains itself.
hidden: false
metadata:
  title: Assign tactics automatically with rules
  keywords:
    - Lifesight Tactics
---
Rules keep your tactics up to date automatically, so every new campaign is measured correctly from the day it launches. Assigning tactics by hand doesn't scale. New campaigns launch every week and each one arrives unclassified, so spend goes unmapped faster than anyone can keep up.

A rule looks for a pattern and assigns a tactic automatically. Most importantly, it applies to campaigns that don't exist yet, so tomorrow's launches are classified the moment they appear.

## Know when rules work best

- **Your campaign names follow a convention,** even a loose one
- **You have more than a handful of campaigns,** so clicking through them isn't sustainable
- **New campaigns launch regularly,** and you don't want to revisit your taxonomy every week
- **Several accounts share a naming convention,** so one rule can cover all of them

For exceptions and the long tail of campaigns that no pattern describes, use [Assign tactics by hand](https://docs.lifesight.io/docs/4-0-wip-assign-tactics-manually).

## Create a rule in a few steps

1. Go to **Data > Data Taxonomy**.

2. Click **Manage rules**.

3. Create a rule and build its conditions.

   A condition combines a dimension, an operator, and a value. Available dimensions include campaign name, channel, objective, and account, plus any custom dimensions you created in Data Transformation. Operators include equals, contains, starts with, is in a list, is empty, and comparisons for numbers and dates.

   **Example:** Where **Campaign Name** contains "NB" and **Channel** is Google, assign **Paid Search Non-Brand**.

4. Review the preview before saving. It shows exactly which campaigns the rule will claim. This is the fastest way to discover that your "NB" convention meant something entirely different in 2023.

5. Save the rule.

## Let new campaigns classify themselves

This is the main reason rules exist, so it's worth understanding exactly how they work.

A rule isn't a one-time bulk action. It's a standing instruction. As the rules manager states at the top, rules automatically assign matching campaigns to a tactic, both now and as new campaigns arrive.

Here's what happens to a campaign launched next Tuesday:

1. The campaign appears in Lifesight on the next sync from the ad platform.
2. Every rule is checked against it.
3. If one rule matches, the campaign is assigned that tactic immediately, with no action needed from you.
4. If several rules match, the one with the highest priority wins. See **Control which rule wins with priority** below.
5. If no rule matches, the campaign stays unassigned and appears in the **New** column.

The **New** column flags campaigns and ad sets created in the last 30 days. Use it as your working list: filter on it, see what your rules didn't catch, and either assign those campaigns by hand or broaden a rule.

Two things follow from this that are easy to miss:

**Rules apply to your history too.** A rule you write today classifies matching campaigns in your historical data as well as future ones, so you don't need a separate backfill (a one-time update of past data).

**A campaign that stops matching loses its rule assignment.** If someone renames a campaign so it no longer matches, it moves to the next rule that matches it, or to no tactic at all. This is why you should check your rules after any bulk rename in the ad platform.

## Control which rule wins with priority

When two rules match the same campaign, priority decides which one applies.

**How priority works**

Priority is a position in an ordered list, not a label you type. The list runs from 1 to N with no gaps, where 1 is the highest priority.

**When several rules match the same campaign, the rule with the lowest priority number wins.**

In the editor, priority runs from top to bottom. The rule at the top has the highest priority and claims a campaign before any rule below it.

**How priority is set when you create a rule**

Rules are always numbered without gaps. If you insert a new rule at position 3, every rule from there down moves down one position. You'll never have two rules in the same position, and you'll never need to renumber them by hand.

**How to change priority**

Open the priority editor from the rules manager. Rules are listed top to bottom in priority order. To reorder them, drag the grip handle on the left of each row. A line shows where the rule will land before you drop it.

You can also move a rule with the keyboard: select its handle and use the up and down arrow keys, where up means higher priority.

Since moving one rule shifts the others, changes are applied together as a set rather than one at a time.

**How to order your rules**

Put the most specific rules at the top and the most general at the bottom.

A rule for one product line should sit above the broad rule for its whole channel. If the broad rule sits higher, it claims everything first and the specific rule never applies.

**Example, in priority order:**

1. **Campaign Name** contains "Brand" and **Channel** is Google, assign **Paid Search Brand**
2. **Campaign Name** contains "NB" and **Channel** is Google, assign **Paid Search Non-Brand**
3. **Channel** is Google, assign **Paid Search Other**

The third rule is a catch-all (a broad rule that picks up anything the rules above it missed). It only classifies Google campaigns the first two didn't claim, which is exactly what you want. If it were at the top, it would claim every Google campaign.

**Exceptions**

You can exclude individual campaigns from a rule when the pattern is right but one campaign is genuinely different. Exclusions stay in place whenever rules are rechecked, and the excluded campaign moves to the next matching rule, or stays unassigned.

## Get reliable results even when names are inconsistent

Rules work best when campaign names follow a pattern. If yours don't, Data Taxonomy will make that very clear, and no amount of clever rule writing will fully fix it.

The real fix is a naming convention going forward, agreed with whoever launches your campaigns. In the meantime, assign your highest-spend campaigns by hand and write rules for the campaigns that do follow a consistent pattern.

## See how rules keep the rest of Lifesight accurate

Over time, rules matter more than manual assignment, because they decide whether your measurement stays accurate without anyone maintaining it.

**Model Schema and Marketing Mix Modeling** use tactics as their paid media variables. When a new campaign launches and nothing classifies it, its spend falls outside every tactic. The model then has spend it can't assign to any variable, which quietly distorts the contributions it reports for the channels that were classified.

**Model Refresh** is where this matters most. A model that refreshes on a schedule keeps running against a taxonomy that slowly goes out of date. Rules keep a refreshed model reading the same structure it was built on.

**Planner and Optimizer** create plans and budget recommendations by tactic. Unclassified spend is invisible to both, so a plan can look balanced while a meaningful share of budget is missing from it.

**Attribution and Analyze dashboards** group results by tactic. Unclassified campaigns collect in an unassigned group, which is usually the first sign that your taxonomy has fallen out of date.

***

## Frequently Asked Questions

**What is a tactic rule in Lifesight?**

A tactic rule automatically assigns campaigns to a tactic when they match a pattern, such as a campaign name that contains "NB." Rules apply to existing campaigns and to new campaigns as they arrive.

**When should I use rules instead of assigning tactics by hand?**

Use rules when your campaign names follow a convention, you have more than a handful of campaigns, new campaigns launch regularly, or several accounts share the same naming convention. Assign tactics by hand for exceptions and one-off campaigns.

**How do I create a rule?**

Go to **Data > Data Taxonomy** and click **Manage rules**. Create a rule, build its conditions, review the preview to see which campaigns it will claim, and save.

**What conditions can a rule use?**

Conditions can use campaign name, channel, objective, account, and any custom dimensions you created in Data Transformation. Operators include equals, contains, starts with, is in a list, is empty, and comparisons for numbers and dates.

**Can I check a rule before saving it?**

Yes, and you should. The preview lists every campaign the rule will claim before you save.

**Do rules classify new campaigns automatically?**

Yes. When a new campaign appears on the next sync, every rule is checked against it. If one matches, the campaign is assigned that tactic immediately.

**What happens if no rule matches a new campaign?**

The campaign stays unassigned and appears in the **New** column, which flags campaigns and ad sets created in the last 30 days. Assign it by hand or broaden a rule to cover it.

**Do rules apply to historical campaigns?**

Yes. A rule classifies matching campaigns in your history as well as new ones, so you don't need a separate backfill.

**What happens when two rules match the same campaign?**

The rule with the lowest priority number wins, meaning the one nearest the top of the list.

**How do I change rule priority?**

Open the priority editor from the rules manager and drag rules into order using the grip handle on each row. You can also select a handle and use the up and down arrow keys. Changes are applied together as a set.

**How should I order my rules?**

Put the most specific rules at the top and the most general at the bottom. A broad catch-all rule should sit last, so it only picks up campaigns the more specific rules missed.

**Can I exclude a campaign from a rule?**

Yes. Exclude individual campaigns when the pattern is right but one campaign is different. The excluded campaign moves to the next matching rule, or stays unassigned. Exclusions stay in place whenever rules are rechecked.

**What happens if a campaign is renamed?**

If a campaign is renamed so it no longer matches its rule, it moves to the next matching rule or becomes unassigned. Manual assignments aren't affected, since they follow the campaign ID.

**What should I check after a bulk rename in the ad platform?**

Check your rules. Manual assignments survive because they follow the campaign ID, but rules written against the old names will stop matching.

**Should I use rules for everything?**

No. Use rules for patterns and manual assignment for exceptions. Trying to capture every exception as a rule creates a rule set nobody can follow.

**What if my campaign names are inconsistent?**

Agree on a naming convention with whoever launches your campaigns going forward. In the meantime, assign your highest-spend campaigns by hand and write rules for campaigns that follow a consistent pattern.

**Why do rules matter for my models?**

Marketing Mix Modeling uses tactics as paid media variables. Unclassified spend can't be assigned to any variable, which distorts the contributions reported for other channels. Rules keep new campaigns classified, especially for models that refresh on a schedule.

**How does unclassified spend affect Planner and Optimizer?**

Planner and Optimizer work by tactic, so unclassified spend is invisible to them. A plan can look balanced while a meaningful share of your budget is missing.

***

## Related Articles

<Cards>
  <Card title="Model Schema" icon="🔗">

  </Card>

  <Card title="Marketing Mix Modeling" icon="🔗">

  </Card>
</Cards>
