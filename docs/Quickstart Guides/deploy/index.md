---
title: 'Deploy: Turn Your Plan Into Budget Decisions'
excerpt: >-
  Review what your measurement recommends, adjust it, and send the change to
  your ad platforms.
deprecated: false
hidden: false
metadata:
  title: Deploy
  robots: index
---
Deploy turns your plan into real budget and bid changes in your ad accounts, so the results your plan forecasts actually reach your campaigns.&#x20;

It answers three questions: how is the plan pacing, what should change, and what happens when you apply it. Today it has one tab, Budget & Bid, covering budget and bid changes at campaign and ad set level.

Recommendations come from Causal Attribution, measured against your promoted plan.

&#x20;They unlock once you have two things: a calibrated incrementality source (a promoted model or an adopted geo experiment) and a promoted plan. Without calibration, there is nothing to recommend against. Without a plan, there is no target to pace toward.

![](https://files.readme.io/d126c593c10d5a52932042358c8fe30637776da57df0a17fd0502065c76ab114-Screenshot_2026-10-23_at_3.44.27_PM.png)

<br />

## See where your plan stands

The plan badge shows the plan's state and length, for example Live, 181-day plan. Four cards then give you the shape of the period before you read a single row.

**Planned Budget** is what the plan allocates. It also shows the percentage change against what is set in your ad accounts today.

**Forecasted Revenue, Forecasted iROAS and Forecasted ROAS** are the outcomes the plan projects. If your workspace optimizes for conversions, you see conversions and iCPA (incremental cost per acquisition) in their place.

**Budget Pace** runs across the full plan window, with today marked on the bar. It shows attributed spend to date against the plan total. It only compares the days that have passed, so being early in a long plan reads as early, not as underspend.

![](https://files.readme.io/a5580704b8abc92747a0063129b9a2f7e43f0141110fbc689c01b262ee472ba4-Screenshot_2026-10-23_at_3.46.27_PM.png)

## Budget & Bid: know what to change, and where

Budget & Bid has two views: Campaigns and Ad Sets. Each entity (a campaign or an ad set) appears in the view where its budget actually lives. You can see this beneath each name as CBO, DAILY budget or ABO, DAILY budget.

* **CBO** (campaign budget optimization): the campaign holds the budget, so the campaign appears and its ad sets do not.
* **ABO** (ad set budget optimization): each ad set holds its own budget, so the ad sets appear and the campaign does not.

Every entity appears in exactly one view: the level where you can actually make a change. If your workspace runs entirely on campaign budgets, the Ad Sets view will be empty, and that is correct.

**What each row shows**

* **Recommendation:** Scale, Reduce or Maintain, with the amount. It comes from the plan's allocation measured against the entity's incremental return, not from platform-reported performance.
* **Current Budget:** what is set on the platform today.
* **Spend:** delivery to date. It tells you whether a recommended change is a small correction or a large swing.
* **Bid Strategy and Bid Target:** the entity's current bidding setup, for example Cost Cap at $15.39. Entities on automated bidding show no target, because there is none to set.
* **Deploy Status:** whether the recommendation has been actioned.

**Find the rows you need**

Filter by channel, tactic (the role a campaign plays, such as prospecting or retargeting) or recommendation type, or search by name. The count beside the filters shows how many rows you are looking at out of the total.

![](https://files.readme.io/de37b82a10cc087f6f120f282337c7ce35036765d02a24dee0574bcfb9661210-Screenshot_2026-10-23_at_3.50.21_PM.png)

## Apply changes in a few clicks

Open a row's menu and choose **Change Budget**, **Change Bid Value** or **Change Status**. To change several rows at once, use **Select multiple**, tick the rows, and apply the same action to all of them from the bar that appears.

The budget dialog opens on **Recommended**. It lists each selected entity with its current budget, the new budget, and the size of the move, for example $1K to $2K, +84%. Switch to **Custom** to type your own figure for each entity instead. Confirm with **Apply Budget Change**.

## Manage bids yourself, for now

You can see and edit bid targets in Deploy, but Lifesight does not recommend them yet. If you open the bid dialog in Recommended mode, every entity shows "no recommendation". Use **Custom** to set a bid target yourself, using the current value shown as your reference.

Bid target recommendations are planned. Until they arrive, use Deploy to see and change your bid settings, and read the Recommendation column as being about budget only.

## Get the most from Deploy

1. Read the header first. If pacing is already off plan, that changes how you read every row below it.
2. Work through the Reduce recommendations before the Scale ones. The budget you recover funds the increases.
3. Check spend against the recommended change. A large move on an entity that has been delivering heavily is worth a second look.
4. Apply changes in bulk where the reasoning is the same across rows, and one at a time where it is not.
5. Come back and check pacing again after a few days. Deploy is a loop, not a one-time exercise.

Recommendations reflect your promoted plan and your promoted incrementality source. Treat them as a considered starting point, not an instruction. Platform delivery behavior, seasonality and commitments outside the plan are context only you have.

## Frequently Asked Questions

**What does Deploy do?**

Deploy turns your promoted plan into budget and bid changes in your ad accounts. It shows how the plan is pacing, recommends what to change, and lets you apply those changes from Lifesight.

**Why can't I see any recommendations?**

Recommendations need two things: a calibrated incrementality source (a promoted model or an adopted geo experiment) and a promoted plan. If either is missing, Deploy has nothing to measure against.

**Where do the recommendations come from?**

They come from Causal Attribution, measured against your promoted plan. Each recommendation compares the plan's allocation with the entity's incremental return, not with platform-reported performance.

**What do Scale, Reduce and Maintain mean?**

Scale means increase the budget, Reduce means lower it, and Maintain means keep it as it is. Each recommendation shows the amount of the change.

**Why does a campaign appear but not its ad sets?**

The campaign uses CBO (campaign budget optimization), so the budget sits at campaign level. Deploy shows each entity only at the level where you can change its budget.

**Why is my Ad Sets view empty?**

Your workspace runs entirely on campaign budgets. Every budget sits at campaign level, so all entities appear in the Campaigns view. This is expected.

**Does Budget Pace show underspend early in a plan?**

No. Budget Pace only compares the days that have passed. Being early in a long plan reads as early, not as underspend.

**What will I see if my workspace optimizes for conversions?**

The header shows forecasted conversions and iCPA (incremental cost per acquisition) instead of Forecasted Revenue, Forecasted iROAS and Forecasted ROAS.

**Can I change budgets for several campaigns at once?**

Yes. Use Select multiple, tick the rows you want, and apply the same action from the bar that appears.

**Can I use my own budget figures instead of the recommended ones?**

Yes. In the budget dialog, switch from Recommended to Custom and type your own figure for each entity.

**Does Lifesight recommend bid targets?**

Not yet. You can see and edit bid targets in Deploy, but the Recommendation column is about budget only. Bid target recommendations are planned.

**Why does an entity show no bid target?**

The entity is on automated bidding, so there is no target to set.

**How do I know if a recommendation has been applied?**

Check the Deploy Status column. It shows whether each recommendation has been actioned.

**How often should I check Deploy?**

Check pacing again a few days after you apply changes. Deploy works best as a regular loop, not a one-time exercise.

**Should I apply every recommendation as it is?**

Treat recommendations as a considered starting point. Platform delivery behavior, seasonality and commitments outside the plan are context only you have, so review before you apply.

## Next up

<Cards>
  <Card title="Deploy Recommedations" href="https://docs.lifesight.io/docs/recommendations" icon="fa-rocket">

  </Card>
</Cards>