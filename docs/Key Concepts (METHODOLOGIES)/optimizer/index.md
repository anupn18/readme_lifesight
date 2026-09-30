---
title: Deploy
excerpt: >-
  Review what your measurement recommends, adjust it, and send the change to
  your ad platforms.
deprecated: false
hidden: true
metadata:
  robots: index
---
Deploy is where a plan stops being a projection and becomes a set of changes in your ad accounts. It answers three questions: how is the plan pacing, what should change, and what happens when you apply it. Today it has one tab, Budget & Bid, covering budget and bid changes at campaign and ad set level.

Recommendations come from Causal Attribution, measured against your promoted plan. They unlock once you have both a calibrated incrementality source (a promoted model or an adopted geo experiment) and a promoted plan. Without calibration there is nothing to recommend against, and without a plan there is no target to pace toward.

\[IMAGE PLACEHOLDER: Deploy header with plan summary and budget pace]

## The header: where the plan stands

The plan badge names the plan's state and length, for example Live, 181-day plan. Four cards then give you the shape of the period before you read a single row. Planned Budget is what the plan allocates, with the percentage change against what is set in your ad accounts today. Forecasted Revenue, Forecasted iROAS and Forecasted ROAS are the outcomes the plan projects. A workspace that optimises for conversions sees conversions and iCPA in their place.

Budget Pace runs the full plan window with today marked on the bar, showing attributed spend to date against the plan total. It compares elapsed days only, so being early in a long plan reads as early rather than as underspend.

\[IMAGE PLACEHOLDER: Campaigns table with recommendations]

## Budget & Bid: every entity, scored and actioned

Two views, Campaigns and Ad Sets. Which one an entity appears in is decided by where its budget actually lives, shown beneath each name as CBO, DAILY budget or ABO, DAILY budget. Under campaign budget optimisation the campaign holds the budget, so the campaign appears and its ad sets do not. Under ad set budget optimisation each ad set holds its own, so the ad sets appear and the campaign does not. Every entity appears in exactly one view, the level where a change can actually be made. A workspace running entirely on campaign budgets will have an empty Ad Sets view, and that is correct.

Each row carries:

* Recommendation: Scale, Reduce or Maintain, with the amount. It is drawn from the plan's allocation measured against the entity's incremental return, not from platform reported performance.
* Current Budget: what is set on the platform today.
* Spend: delivery to date, the context for whether a recommended change is a small correction or a large swing.
* Bid Strategy and Bid Target: the entity's current bidding setup, for example Cost Cap at $15.39. Entities on automated bidding show no target, because there is none to set.
* Deploy Status: whether the recommendation has been actioned.

Filter by channel, tactic or recommendation type, or search by name. The count beside the filters tells you how many rows you are looking at out of the total.

\[IMAGE PLACEHOLDER: Row menu and the Change Campaign Budget dialog]

## Making a change

Open a row's menu for Change Budget, Change Bid Value or Change Status. Or use Select multiple to tick several rows and apply the same action across all of them from the bar that appears.

The budget dialog opens on Recommended, listing each selected entity with its current budget, the new one, and the size of the move, for example $1K to $2K, plus 84 percent. Switch to Custom to type your own figure per entity instead. Confirm with Apply Budget Change.

## Bidding: view and change, not recommend

Bid targets are shown and can be edited, but the platform does not recommend them. Opening the bid dialog in Recommended mode prints "no recommendation" against every entity, because no recommended bid value is produced anywhere in the pipeline yet. Use Custom to set a bid target yourself against the current value shown.

Bid target recommendations are planned. Until they ship, treat bidding in Deploy as a place to see and change what is set, and read the Recommendation column as being about budget only.

## How to use the results

1. Read the header first. If pacing is already off plan, that changes how you read every row beneath it.
2. Work the Reduce recommendations before the Scale ones. Recovered budget funds the increases.
3. Check spend against the recommended change. A large move on an entity that has been delivering heavily is worth a second look.
4. Apply in bulk where the reasoning is the same across rows, one at a time where it is not.
5. Come back and re-read pacing after a few days. Deploy is a loop, not a one-time exercise.

Recommendations reflect your promoted plan and your promoted incrementality source. They are a considered starting point rather than an instruction. Platform delivery behaviour, seasonality and commitments outside the plan are context only you have.

\[VIDEO PLACEHOLDER: Reviewing recommendations and deploying a budget change]

<br />
