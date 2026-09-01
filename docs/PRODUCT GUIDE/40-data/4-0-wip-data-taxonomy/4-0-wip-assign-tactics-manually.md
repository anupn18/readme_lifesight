---
title: '[4.0][WIP] Assign tactics by hand'
excerpt: >-
  Classify campaigns into tactics one selection at a time, which is the fastest
  way to cover most of your spend on day one.
hidden: true
---
Manual assignment is how most people start, and it is the right choice for the first pass and for the awkward long tail that no rule will ever catch cleanly.

The goal is not to classify every campaign. It is to classify the campaigns that carry the money.

## When to use it

- **Your first pass**, before you know what patterns exist in your campaign names
- **The long tail** of small or one off campaigns that do not fit any pattern
- **Exceptions** where a campaign's name says one thing and it is actually doing another
- **Small accounts** where a handful of campaigns cover everything

For anything that repeats, and for campaigns that do not exist yet, use [Assign tactics automatically with rules](https://docs.lifesight.io/docs/4-0-wip-assign-tactics-rules) instead.

## How to do it

1. Go to **Data > Data Taxonomy**.
2. Stay on the **Tactic mapper** sub-tab, **Campaigns** view.
3. Sort by **Spend**, highest first. This is the single most useful thing you can do, because it puts your budget at the top of the screen.
4. Tick the campaigns that belong to the same tactic. You can select several at once.
5. Assign the tactic to the whole selection.
6. Save your changes.

![The Tactic mapper with campaigns ready to be assigned](https://files.readme.io/40c936dd49cf910b84fef6342458da83dd6e4252ceb1fd7cf5a35da5aac9c922-taxonomy-mapper.png)

Repeat down the list. Watch the **spend mapped** percentage along the bottom rather than the campaign count. Classifying 80 percent of campaigns means very little if they are the ones spending nothing, while 95 percent of spend mapped is real progress.

## Working at ad set level

Switch to **Ad Sets** when one campaign genuinely contains more than one tactic. This is most common on Meta, where prospecting and retargeting audiences frequently share a campaign.

The ad set is the unit a tactic really attaches to. A campaign owns several, and what you see in the Campaigns view is a roll-up of what its ad sets say. Assigning a tactic to a campaign assigns it to all of them.

### Finding partially mapped campaigns

Because ad sets are mapped individually, a campaign can end up half done. Four of its five ad sets carry a tactic and the fifth does not, usually because it was created after you last looked.

This is the failure that costs you real money, and it is quiet. Nothing errors. The campaign does not look unmapped. The spend in that fifth ad set simply never reaches the model.

The mapper keeps these states distinct rather than collapsing them:

- **Fully mapped** and **Fully mapped, split** are both fine. Split just means the ad sets legitimately carry different tactics.
- **Partially mapped** and **Partially mapped, split** are the ones to fix.

Use the Tactic column's status filter to show the partial states, then open the Tactic cell on any campaign it returns. The breakdown tells you how many ad sets are mapped, to which tactics, and how much spend is sitting unclassified underneath.

Doing this once a month catches the campaigns that quietly grew a new ad set.

Only drop to ad set level deliberately, though. A campaign genuinely doing two jobs deserves the split. Splitting one that does not is extra maintenance for no gain.

## Choosing the tactics themselves

There is no correct list. A good rule of thumb: **create a tactic when you would plausibly change its budget independently of everything else.**

If you never move money between brand and non-brand search, splitting them buys you nothing. If you argue about it every quarter, split them.

Start coarse. Half a dozen tactics that everyone understands beats thirty that nobody maintains, and you can always split a tactic later.

## Where this shows up in the rest of Lifesight

Tactics are not a reporting label. They are the unit that several parts of the platform actually operate on.

**Model Schema** defines paid media variables by channel and tactic. A tactic that does not exist here cannot be selected there, so unclassified spend simply cannot enter a model as its own variable.

**Marketing Mix Modeling** estimates a separate contribution and a separate saturation curve for each tactic you defined. This is where the work pays off. If brand and non-brand search are one tactic, the model returns one blended return that describes neither, and the brand campaigns will flatter the prospecting ones. Split them and you get two honest answers.

**Channel Deep Dive and Campaigns** reporting groups performance the way you classified it, which is why the taxonomy should match how your team actually talks about the marketing.

**Planner** builds media plans in terms of these tactics, so the scenarios it produces are only as actionable as the taxonomy is realistic.

**Optimizer** actions budget changes against them. A recommendation to shift budget into a tactic is only useful if that tactic corresponds to something you can genuinely turn up.

**Attribution** uses the same grouping, so classifying once keeps modelled and attributed views talking about the same things.

## Common questions

**What happens to campaigns I never classify?**
They stay unassigned. Their spend is still recorded, but they cannot be measured as a tactic, so a model cannot separate their effect.

**Can a campaign belong to two tactics?**
No, one tactic per campaign. If it is genuinely doing two jobs, split it at ad set level.

**I renamed a campaign in the platform. Do I lose its tactic?**
No. Assignments follow the campaign ID rather than its name.

**Does this change my campaigns?**
No. Nothing here writes back to the ad platform.

**How often should I come back?**
Monthly is plenty. Sort by the **New** column, classify what has appeared, and you are done in a few minutes.