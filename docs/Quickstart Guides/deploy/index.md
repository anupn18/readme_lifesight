---
title: 'Deploy: Review and Apply Budget and Bid Changes'
excerpt: >-
  Review what your measurement recommends, adjust it, and send the change to
  your ad platforms.
deprecated: false
hidden: false
metadata:
  title: Deploy
  robots: index
---
Deploy turns your promoted plan into changes on your ad accounts. This guide shows you how to review the recommendations, apply budget and bid changes, pause ads that are losing money, and check what changed.

**Before you start**

* A calibrated incrementality source: a promoted model or an adopted geo experiment.
* A promoted plan.
* A connected ad account for each platform you want to change from Lifesight.

## What Deploy supports

**Platforms**

| What you can do | Platforms |
| --- | --- |
| Apply budget, bid target and status changes from Lifesight | Google Ads, Meta, Snapchat |
| Pause ads from the Creative tab | Google Ads, Meta |
| See recommendations and apply them yourself in the ad platform | TikTok, Pinterest, LinkedIn, Microsoft Ads |
| Edit geo targeting from Deploy | Coming soon |

**What's automated**

* Recommendations are built every day from your promoted plan and Causal Attribution: Scale, Reduce or Maintain for each campaign and ad set, for the next 7 days.
* Deploy works out where each budget lives (the campaign for CBO, the ad set for ABO), so every change goes to the right level.
* Bid target recommendations come with budget increases when a campaign or ad set isn't spending its current budget.
* Applied changes are pushed to the ad platform for you, for one row or many at once.
* Every applied change is recorded in Logs.

Deploy never changes your ad accounts on its own. Every change needs someone to review and apply it.

**Human checks and controls**

* **Review before you apply.** Every dialog shows the current and new value for each row, the size of the move and the total against your plan.
* **Use your own number.** Switch from Recommended to Custom to set your own budget or bid.
* **Budget only, or budget and bid.** When a bid change is recommended, you choose whether to apply it.
* **Warnings before you apply.** Deploy flags budget increases over 25% and bid changes large enough to restart platform learning.
* **Bid guardrails.** A bid change is only recommended when the budget is going up and the campaign spends under 85% of it. Bids are only loosened, by at most 20% per step, with a 7-day wait after each change.
* **Clear results.** Changes that fail keep their previous value, and you can see which ones failed.
* **A full record.** Logs shows what changed, who changed it and when.

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

   ![](https://files.readme.io/352e0d42bfb781dd477a90035bd740e7299b53694442774ee1f4348eef830d57-screenshot-1792757626130-fff693d7.png)

9. **Come back in a few days.** Recheck pacing and new recommendations. Deploy works best as a regular loop.

## Apply a bid recommendation

When a campaign isn't spending the budget it already has, raising the budget won't help on its own. Its bid target is often what's holding it back. So when Deploy recommends a budget increase for a campaign or ad set that spent less than 85% of its budget over the last 7 days, it also recommends loosening the bid target.

1. Open **Change Budget** for a row with a **Scale** recommendation.
2. If a bid change is recommended, the dialog offers **Review bid changes**. Select it.

   ![](https://files.readme.io/1555f08514dd654707b2ea85718d602b9b465b80c2863afd895d863c1fac99ba-screenshot-1792757654660-dc0d614a.png)
3. Check each row's strategy, current target and new target. A ROAS target goes down and a CPA or cost target goes up, by at most 20% in one step. **Moving towards** means the full move is larger, so it comes in steps.
4. Keep the recommendation, or switch to **Custom** to set your own target.
5. Select **Apply budget and bid**. To change the budget only, go back and apply the budget on its own.

Bid recommendations cover strategies with a target: Target ROAS, Target CPA, Cost Cap, Minimum ROAS and Target Cost. Automated strategies and bid caps are left as they are, and Deploy never tightens a bid. Bid changes restart platform learning, so give delivery a few days to settle. Deploy waits 7 days after a bid change before it recommends another.

## Pause an ad that's losing money

1. Open the **Creative** tab.
2. Review the pause candidates. **Underperforming** ads are losing money against breakeven. **Fatigued** ads have a worn-out audience, for example a falling CTR.
3. Check weekly spend, KPI against the average, strength, fatigue status and the reason to pause.
4. Select **Pause ad** and confirm. Pausing is available for Google and Meta ads.

   ![](https://files.readme.io/16eb8f0411cfe27399a56562e8f494ccc9affd556a7efe28de510fb288146339-screenshot-1792757748993-9ec97aca.png)

The Creative tab also shows the estimated spend you can recover each week by pausing.

## If something doesn't look right

* **No recommendations.** Check that you have a promoted model or an adopted geo experiment, and a promoted plan. After you promote a new plan, its recommendations appear after the next daily update.
* **The Ad Sets view is empty.** Your campaigns hold their own budgets (CBO), so everything shows under Campaigns. This is expected.
* **No bid recommendation on a row.** The budget isn't going up, the row is already spending its budget, its strategy has no target to change, or its bid changed in the last 7 days.
* **A change failed.** The row keeps its previous value. Check Logs, then try again.

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

**Geo Targeting** lists the campaigns and ad sets from your plan, with their ad account, current geo targeting and last geo change. Live geo targeting edits from Deploy are coming soon.

## Get the most from Deploy

1. Read the header first. If pacing is already off plan, that changes how you read every row below it.
2. Work through the Reduce recommendations before the Scale ones. The budget you recover funds the increases.
3. Check spend against the recommended change. A large move on an entity that has been delivering heavily is worth a second look.
4. Apply changes in bulk where the reasoning is the same across rows, and one at a time where it is not.
5. Come back and check pacing again after a few days. Deploy is a loop, not a one-time exercise.

Recommendations reflect your promoted plan and your promoted incrementality source. Treat them as a considered starting point, not an instruction. Platform delivery behavior, seasonality and commitments outside the plan are context only you have.

## Frequently Asked Questions

**What does Deploy do?**

Deploy connects your promoted plan to your ad accounts. It shows how the plan is pacing, recommends what to change in each campaign and ad set, and lets you apply those changes from Lifesight.

**Which ad platforms can Deploy change?**

Budget and bid changes go live on Google, Meta and Snapchat. For other platforms, Deploy shows the recommendation for you to apply in the platform. Pausing ads from the Creative tab is available for Google and Meta.

**Does Deploy change anything automatically?**

No. Every change needs someone to review and apply it. Applied changes go live on the ad platform straight away and are recorded in Logs.

**What happens if some changes fail?**

Changes that succeed go live. Changes that fail keep their previous value. Check Logs, then try again.

**How do I get started with Deploy?**

Select Deploy in the left navigation, read the header to check pacing, then review the recommendations in Budget & Bid and apply the ones you agree with.

**Why can't I see any recommendations?**

Recommendations need two things: a calibrated incrementality source (a promoted model or an adopted geo experiment) and a promoted plan. If either is missing, Deploy has nothing to measure against. After you promote a new plan, its recommendations appear after the next daily update.

**What time period do recommendations cover?**

Budget recommendations cover the next 7 days and refresh once a day.

**What does Budget recommendations outstanding mean?**

It shows how many recommendations are waiting for action, out of all actionable entities in the plan.

**What do Scale, Reduce and Maintain mean?**

Scale means move the budget up, Reduce means lower it, and Maintain means keep it as it is. Each recommendation shows the target budget.

**Why does a campaign appear but not its ad sets?**

The campaign uses CBO (campaign budget optimization), so the budget sits at campaign level. Deploy shows each entity only at the level where you can change its budget.

**Why is my Ad Sets view empty?**

Your workspace runs entirely on campaign budgets, so all entities appear in the Campaigns view. This is expected.

**Does Budget Pace show underspend early in a plan?**

No. Budget Pace only compares the days that have passed. Being early in a long plan reads as early, not as underspend.

**Can I change budgets for several campaigns at once?**

Yes. Use Select multiple, tick the rows you want, and apply the same action from the bar that appears.

**Can I use my own budget figures instead of the recommended ones?**

Yes. In the budget dialog, switch from Recommended to Custom and type your own figure for each entity.

**Does Lifesight recommend bid targets?**

Yes, alongside budget increases, when a campaign or ad set isn't spending its current budget and its strategy has a target. The target moves toward what the plan expects the next dollar to return, at most 20% at a time. See Apply a bid recommendation above.


**Can I edit geo targeting from Deploy?**

Not yet. The Geo Targeting tab shows current targeting for each campaign and ad set. Live edits from Deploy are coming soon.

**What does the Creative tab show?**

Ads that Creative Intelligence flags as pause candidates, split into underperforming and fatigued, with the spend you can recover each week.

**How do I check what was changed?**

Open Logs from the Deploy header. Every applied change is recorded with what changed, who changed it and when.

**Should I apply every recommendation as it is?**

Treat recommendations as a considered starting point. Platform delivery behavior, seasonality and commitments outside the plan are context only you have, so review before you apply.