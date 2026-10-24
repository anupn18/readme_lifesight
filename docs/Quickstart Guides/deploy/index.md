---
title: 'Deploy: Review and Apply Budget and Bid Changes'
excerpt: >-
  Review what your measurement recommends, adjust it, and send the change to
  your ad platformforms.
deprecated: false
hidden: false
metadata:
  title: Deploy
  robots: index
---
Deploy turns your promoted plan into budget and bid changes on your ad accounts. This guide shows you how to review the recommendations, apply budget and bid changes, update statuses, pause ads that are losing money, and check what changed.

**Before you start**

* A promoted model, calibrated in Causal Attribution.
* A promoted plan.
* A connected ad account for each platform you want to change from Lifesight.

## What Deploy supports

**Platforms**

| What you can do from Deploy | Google Ads | Meta | Snapchat | TikTok | Pinterest |
| --- | --- | --- | --- | --- | --- |
| Change budgets | Campaigns | Campaigns and ad sets | Campaigns and ad squads | Campaigns and ad groups | Campaigns and ad groups |
| Change bid targets | Campaigns on Target CPA, Target ROAS or Maximize Conversion Value; ad groups on Manual or Enhanced CPC | Campaigns and ad sets | Ad squads | Ad groups | Ad groups |
| Change status (active or paused) | Campaigns and ad groups | Campaigns and ad sets | Campaigns and ad squads | Campaigns and ad groups | Campaigns and ad groups |
| Pause ads from the Creative tab | Yes | Yes | Not yet | Not yet | Not yet |

Other channels in your plan still get budget recommendations in Deploy, but their rows can't be selected. Apply those changes in the ad platform. Geo targeting is view-only in Deploy for now.

**What's automated**

* Recommendations are refreshed once a day from Causal Attribution, measured against your promoted plan: Scale, Reduce or Maintain for each campaign and ad set, with the budget for the next 7 days.
* Deploy shows each campaign or ad set where its budget lives (the campaign for CBO, the ad set for ABO), so every change goes to the right level.
* When a campaign or ad set is due a budget increase but spent less than 85% of its budget over the last 7 days, Deploy also recommends loosening its bid target, so the extra budget can be spent.
* When you apply, Deploy pushes the change to the ad platform for you, for one row or many at once.
* Every applied change is recorded in Logs.

Deploy never changes your ad accounts on its own: every change needs someone to review and apply it.

**Human checks and controls**

* **Review before you apply.** The dialog lists each selected row with its current and new value. For budgets in Recommended mode, it also shows the size of the move.
* **Use your own number.** Switch from Recommended to Custom to set your own budget or bid target.
* **Budget only, or budget and bid.** When a bid change is recommended, you choose whether to apply it with the budget.
* **Bid guardrails.** Bids are only ever loosened, toward the return the plan expects from the next dollar, by at most 20% per step. After a bid change, Deploy waits 7 days before recommending another.
* **Only what can change.** Rows that can't take the change you picked are left out, and the dialog tells you how many.
* **Permissions.** Changing budgets and bids, and changing statuses, are separate permissions. People without them don't see these actions.
* **Check each result.** After you apply, each row's Deploy Status shows whether the change went through.
* **Pause with care.** When a pause would remove more than half of a tactic's pause-candidate spend, Deploy warns you first. You can undo a pause from the row before you leave the page.
* **A full record.** Logs shows who made each change, the entity, the action, the value before and after, and the outcome.

## Put your plan into action

1. Select **Deploy** in the left navigation.

2. **Check where your plan stands.** Read the header first. Compare Planned Budget with your current budget, check the forecasted outcomes, and look at Budget Pace to see if spend is on track.

   ![](https://files.readme.io/177b93679538cf24befc016d024a4a006d94ff1367a17b07a49ad441278c67e8-deploy-step-2-plan-header.png)

3. **See how much needs action.** The **Budget recommendations outstanding** card shows how many recommendations are waiting, out of all actionable entities (campaigns or ad sets that can take a change).<br />

   ![](https://files.readme.io/d24a91a6fcd8992d172b494828f83d9a9385d995bd97a7ca191b65f91f71129b-screenshot-1792757442083-88c96a53.png)

4. **Pick the right view.** In **Budget & Bid**, choose **Campaigns** or **Ad Sets**. Each entity shows in the view where its budget lives.<br /><br />

   ![](https://files.readme.io/d76d36c12a1fa989cf3991d8ef2e6f266c318166637c81312585ec95d4e8105e-screenshot-1792757517640-3a8fce16.png)

5. **Narrow the list.** Filter by channel, tactic or recommendation type, or search by campaign name.<br />

   ![](https://files.readme.io/ebea7ebe8359e887ab2927d46313192006cba8d7e7fa10bdcf79f552604cf5c0-screenshot-1792757562017-e1aa81fc.png)

6. **Review each recommendation.** Compare the recommended budget with **Current Budget**, **Spend (Last 7d)** and **Budget Utilisation** before you act.

   ![](https://files.readme.io/98ac963ef4d245f549ccd09779400fb545f19c83ffd25250753f5cbe3d92918d-screenshot-1792757529079-9e8e2aab.png)

7. **Apply changes.** Open a row's menu to change one entity, or use **Select multiple** to apply the same action to several rows. Take the recommended figure or switch to **Custom** to enter your own.<br />

   ![](https://files.readme.io/ffea2a32bb88ba85c6e1c3c7a1ccc8507899646e5bab712eca938209428b0274-screenshot-1792757599788-f67bc2be.png)

8. **Confirm and verify.** Check current against new values in the confirmation step, apply, then open **Logs** from the Deploy header to see what changed, who changed it and when.<br />

   ![](https://files.readme.io/1e5a9c653106425ee06c7c3e498b1c0f8f9093e0d52d2d58f870176342e18690-deploy-step-8-budget-dialog.png)

9. **Come back in a few days.** Recheck pacing and new recommendations. Deploy works best as a regular loop.

## Apply a bid recommendation

When a campaign isn't spending the budget it already has, raising the budget won't help on its own. Its bid target is often what's holding it back. So alongside a budget increase, Deploy recommends loosening the bid target for campaigns and ad sets that spent less than 85% of their budget over the last 7 days.

**How Deploy works out a bid recommendation**

A bid change is recommended only when all three are true:

* The plan recommends a budget increase for the campaign or ad set.
* It spent less than 85% of its budget over the last 7 days.
* Its strategy has a target Deploy can move, such as Target ROAS, Target CPA, Cost Cap or Target Cost.

The new target moves toward the plan's marginal return: the return (or cost per conversion) the plan expects from the next dollar spent in that channel. A ROAS target is lowered toward the plan's marginal ROAS, and a CPA or cost target is raised toward the plan's marginal CPA, by at most 20% in one step. If the target is already at or past the plan's marginal, there's no bid change, because the bid isn't what's holding delivery back. After a bid change, Deploy waits 7 days before recommending another, so the platform can settle.

**Apply it**

1. Open **Change Budget** for a row with a **Scale** recommendation.
2. If a bid change is recommended, the dialog offers **Review bid changes**. Select it.

   ![](https://files.readme.io/b98ccef8bf895b563afc403370e9f2be61398712954f4a0f55642d5ce6076661-deploy-bid-dialog.png)
3. Check each row's strategy, current target and new target. A ROAS target goes down and a CPA or cost target goes up, by at most 20% in one step. **Moving towards** shows where the target is heading when the full move is larger than one step.
4. Keep the recommendation, or switch to **Custom** to set your own target.
5. Select **Apply budget and bid**. To change the budget only, go back and apply the budget on its own.

Bid recommendations cover strategies with a target, such as Target ROAS, Target CPA, Cost Cap and Target Cost. Automated strategies and bid caps are left as they are. Bid changes restart platform learning, so give delivery a few days to settle.

**Set a bid target yourself**

Open a row's menu and choose **Change Bid Value**, switch to **Custom**, enter the new target, and apply. Rows on automated bidding have no target to change.

## Pause an ad that's losing money

1. Open the **Creative** tab.
2. Review the pause candidates. **Underperforming** ads are losing money against breakeven. **Fatigued** ads have a worn-out audience, for example a falling CTR.
3. Check weekly spend, KPI against the average, strength, fatigue status and the reason to pause.
4. Select **Pause ad** and confirm. Pausing is available for Google Ads and Meta ads.

   ![](https://files.readme.io/16eb8f0411cfe27399a56562e8f494ccc9affd556a7efe28de510fb288146339-screenshot-1792757748993-9ec97aca.png)

The Creative tab also shows the estimated spend you can recover each week by pausing.

## If something doesn't look right

* **No recommendations.** Check that you have a promoted model calibrated in Causal Attribution and a promoted plan. After you promote a new plan, its recommendations appear after the next daily update.
* **A row can't be selected.** Deploy can't change that channel or that field yet. Apply the change in the ad platform.
* **No bid recommendation on a row.** The budget isn't going up, the row is already spending 85% or more of its budget, its strategy has no target to change, or its bid changed in the last 7 days.
* **The Ad Sets view is empty.** Your campaigns hold their own budgets (CBO), so everything shows under Campaigns. This is expected.
* **A change didn't go through.** Check the row's Deploy Status and Logs, then try again.

## Reference: what you see in Deploy

**The header**

* **Plan badge**: the plan's state and length, for example Live, 92-day plan.
* **Planned Budget**: what the plan allocates, with the change against your current budget over the plan period.
* **Forecasted Revenue** and **Forecasted iROAS**: the outcomes the plan projects. Workspaces that optimize for conversions see conversions and iCPA (incremental cost per acquisition) instead.
* **Budget recommendations outstanding**: how many recommendations are waiting, out of all campaigns and ad sets that can take a change.
* **Budget Pace**: attributed spend to date against the plan total, with today marked (for example Wk 1, Day 3). It only compares the days that have passed, so being early in a long plan reads as early, not as underspend.

**Campaigns and Ad Sets**

Each campaign or ad set appears in the view where its budget lives. You can see this beneath each name, for example CBO, DAILY budget.

* **CBO** (campaign budget optimization): the campaign holds the budget, so the campaign appears and its ad sets do not.
* **ABO** (ad set budget optimization): each ad set holds its own budget, so the ad sets appear and the campaign does not.

**Each row**

* **Tactic**: the role the campaign plays, such as prospecting or retargeting, from your taxonomy mapping.
* **Recommendation**: Scale, Reduce or Maintain, with the target budget for the next 7 days. It comes from the plan's allocation measured against the row's incremental return, not from platform-reported performance.
* **Current Budget**: what is set on the platform today.
* **Spend (Last 7d)**: delivery over the last 7 days. It tells you whether a recommended change is a small correction or a large swing.
* **Budget Utilisation**: how much of the current budget is being spent.
* **Bid Strategy** and **Bid Target**: the current bidding setup, for example Target CPA at $42.00. Automated strategies show no target, because there is none to set.
* **Deploy Status**: whether the recommendation has been actioned, for example Pending.

**Geo Targeting** lists the campaigns and ad sets from your plan, with their ad account, current geo targeting and last geo change. Editing geo targeting from Deploy is coming soon.

## Get the most from Deploy

1. Read the header first. If pacing is already off plan, that changes how you read every row below it.
2. Work through the Reduce recommendations before the Scale ones. The budget you recover funds the increases.
3. Check spend against the recommended change. A large move on an entity that has been delivering heavily is worth a second look.
4. Apply changes in bulk where the reasoning is the same across rows, and one at a time where it is not.
5. Come back and check pacing again after a few days. Deploy is a loop, not a one-time exercise.

Recommendations reflect your promoted plan and your promoted incrementality source. Treat them as a considered starting point, not an instruction. Platform delivery behavior, seasonality and commitments outside the plan are context only you have.

## Frequently Asked Questions

**What does Deploy do?**

Deploy connects your promoted plan to your ad accounts. It shows how the plan is pacing, recommends budget and bid changes for each campaign and ad set, and lets you apply them from Lifesight.

**Which ad platforms can Deploy change?**

Google Ads, Meta, Snapchat, TikTok and Pinterest. See the Platforms table above for what you can change on each. Other channels in your plan show budget recommendations that you apply in the ad platform.

**Does Deploy change anything automatically?**

No. Every change needs someone to review and apply it. Applied changes go live on the ad platform and are recorded in Logs.

**Why can't I see any recommendations?**

Recommendations need a promoted model calibrated in Causal Attribution and a promoted plan. After you promote a new plan, its recommendations appear after the next daily update.

**What time period do recommendations cover?**

Budget recommendations cover the next 7 days and refresh once a day.

**What do Scale, Reduce and Maintain mean?**

Scale means move the budget up, Reduce means lower it, and Maintain means keep it as it is. Each recommendation shows the target budget.

**Does Lifesight recommend bid targets?**

Yes, alongside budget increases, when a campaign or ad set isn't spending its current budget and its strategy has a target. The target moves toward what the plan expects the next dollar to return, at most 20% at a time. You can also set a bid target yourself with Custom.

**Can I use my own budget figures instead of the recommended ones?**

Yes. In the budget dialog, switch from Recommended to Custom and type your own figure for each row.

**Why does a campaign appear but not its ad sets?**

The campaign uses CBO (campaign budget optimization), so the budget sits at campaign level. Deploy shows each campaign or ad set only at the level where you can change its budget.

**Can I undo a change?**

You can undo an ad pause from the Creative tab before you leave the page. Budget, bid and status changes can't be undone from Deploy; apply a new change instead. Every change is recorded in Logs.

**How do I check what was changed?**

Open Logs from the Deploy header. Every applied change is recorded with who made it, what changed, the value before and after, and the outcome.

**Should I apply every recommendation as it is?**

Treat recommendations as a considered starting point. Platform delivery behavior, seasonality and commitments outside the plan are context only you have, so review before you apply.