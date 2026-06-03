---
title: MCP Prompt Library
excerpt: >-
  A copy-paste prompt library for using Lifesight MCP to answer planning,
  channel, anomaly, executive, methodology, and BFCM questions.
deprecated: false
hidden: false
metadata:
  title: Lifesight MCP Prompt Library
  description: A collection of proven prompts for measurement, optimization, and planning
  keywords:
    - Lifesight
    - MCP
    - Prompt
    - ''
  robots: index
---
24 prompts. Organized by the decision you're trying to make, not the role you have. Every prompt is copy-paste runnable in Claude or ChatGPT once Lifesight MCP is installed.

## How to use these prompts<br />

**Each prompt is paired with:**

- When to use it - the trigger that should send you here.
- The prompt - copy as-is, or edit the bracketed slots.
- What you'll get back - the shape of Mia's answer.
- What to do next - the suggested follow-up.

**Tools the prompts call:**

- list\_models - workspace inventory.
- search\_knowledge\_base - methodology, past experiments, Lifesight docs.

***

## **1. Channel deep-dive**

The decisions you have to make in the next eight weeks.<br />**<br />1.1 Where to move the next 20% of Q4 spend**

When to use it. You're locking Q4 budget this week and want a defensible reallocation before the auction tightens.

> 📘 Prompt
>
> (`` ` ``Stress-test my \[Quarter] plan. Where am I over-investing relative to<br />incrementality, and what would moving \[%] of that spend to higher-iROAS<br />channels look like in incremental revenue and CAC?`` ` ``)
>
>

**What you'll get back:&#x20;**&#x41; ranked table of over-invested channels with current iROAS, recommended deltas, and the projected incremental revenue lift. Methodology footnote underneath.

**Next step:&#x20;**&#x50;aste the table into your Q4 plan doc. Save the answer with save\_insight so you can re-pull it after the change is live.

***

**1.2 The retargeting trap check**<br /><br />When to use it. Your team is defending a retargeting line item because the platform ROAS looks great.

> 📘 Prompt
>
> For my last  \[weeks] of retargeting spend, show me platform-reported<br />ROAS vs Lifesight iROAS by ad set. Flag every ad set where the gap is<br />greater than 2x.

**What you'll get back:&#x20;**&#x54;wo-column comparison with gap highlighted. Mia adds a sentence on which retargeting audiences are most likely to be cannibalizing organic conversions.

**Next step:** Send the table to your media buyer with a "pause or cap?" tag on each flagged row.

**1.3 The discount-or-brand decision**<br /><br />When to use it. Finance wants a discount; brand wants upper-funnel; you have to choose.

> 📘 Prompt.
>
> Simulate two \[Quarter] scenarios on my live model: (A) repeat last year's<br />\[%] sitewide discount, (B) hold price and shift the discount budget<br />to upper-funnel video. Show incremental revenue, gross margin impact,<br />and projected \[Quarter] carryover for each.

**What you'll get back:&#x20;**&#x41; two-column scenario comparison with the carryover number isolated - this is usually the line that wins the argument.

**Next step:&#x20;**&#x54;ake both scenarios into the planning meeting. Save the answer so you can revisit it in February.

&#x31;**.4 The Q1 cliff stress test**<br /><br />**When to use it:&#x20;**&#x59;ou want to make sure your Q4 plan doesn't strand you in January.

> 📘 Prompt
>
> Based on my current \[Quarter] plan, project the \[Quarter] baseline assuming we cut<br />upper-funnel investment by \[%] in week 1 of \[month]. Where does the<br />revenue floor land? What's the brand-led investment in \[Quarter] that would<br />raise that floor by \[%]?

**What you'll get back:&#x20;**&#x41; projection chart description with two scenarios and a callout of the specific Q4 line items that drive the Q1 floor.

**Next step:&#x20;**&#x55;se this as your Q1 insurance line in your Q4 board memo.

***

## **2. Channel deep-dive**

When one channel is acting weird and you need to know if it's real.<br />**<br />2.1 The "why did this channel spike" question**<br />When to use it. A channel jumped 30%+ week-over-week and you don't know if it's incremental or correlational.

> 📘 Prompt
>
> \[Channel] spend was up \[X]% last week and reported ROAS was up \[Y]%.<br />What does my causal model say about the actual incremental change?<br />Was the lift real, was it pulled from another channel, or was it<br />correlation with \[seasonal event / promo]?

**What you'll get back: &#x20;**&#x41; causal decomposition: incremental contribution, cannibalization from adjacent channels, and external-factor contribution.

**Next step:&#x20;**&#x49;f the lift is real, plan to test scaling. If it's cannibalization, flag the channel mix for review.

**2.2 The cross-channel cannibalization map**<br /><br />When to use it. You want to know which of your "winning" channels are stealing credit from others.

> 📘 Prompt
>
> For my top \[5 channels] by spend, show me the cannibalization matrix:<br />which channels are taking credit for conversions that other channels<br />caused? Rank by total mis-credited revenue.

**What you'll get back:&#x20;**&#x41; 5×5 matrix or ranked list. Most teams discover that 1-2 channels are credit-thieves and 1-2 are credit-victims.

**Next step**: Recalibrate channel-level KPIs to net of cannibalization. Save the matrix for the next attribution debate.

**2.3 The "is this new channel ready to scale" question**<br /><br />When to use it. You're testing a new channel (CTV, retail media, podcasts) and need to decide whether to 5x it.

> 📘 Prompt
>
> For \[new channel], summarize the incremental contribution since launch.
> At what spend level does my causal model expect saturation to begin?
> What's the recommended next-quarter budget cap based on the saturation
> curve?

**What you'll get back:&#x20;**&#x41; spend-vs-iROAS curve description, a saturation point, and a recommended cap.

**Next step:&#x20;**&#x53;et the next-quarter cap below the saturation point. Plan a holdout test if confidence in the model is below 80%.

**2.4 The channel deprecation check**<br /><br />When to use it. Before you kill a channel, make sure your platform numbers aren't hiding its real value.

> 📘 Prompt
>
> \[Channel] looks like an underperformer on platform ROAS. What does my
> causal model say about its true incremental contribution, including
> brand halo, view-through impact, and effect on downstream channels?

**What you'll get back:&#x20;**&#x54;rue incremental contribution plus second-order effects on other channels.

**Next step:** If second-order effects are large, propose a 50% cut instead of a full kill. Save the analysis so you can re-test in 90 days.<br />

***

## **3. Anomaly triage**

Something looks off. Was it real or was it noise?<br /><br />**3.1 The morning anomaly check**<br /><br />When to use it. Slack lit up at 9am because a number moved.

> 📘 Prompt
>
> Find every channel where incremental contribution deviated more than
> 2 standard deviations from forecast in the last 7 days. For each,
> say whether the deviation crosses the threshold for action and what
> the recommended next step is.

**What you'll get back:&#x20;**&#x41; short list of real anomalies, each tagged "act" or "noise" with reasoning.

**Next step:&#x20;**&#x54;riage the "act" list with your team. Save the response as your morning briefing.

**3.2 The campaign-level fatigue check**<br />
When to use it. Performance is degrading and you suspect creative fatigue.

> 📘 Prompt
>
> For \[campaign], show me incremental CPA week-over-week for the last<br />\[8 weeks]. Identify when fatigue began and which creative cohorts are<br />the primary contributors.

**What you'll get back:&#x20;**&#x41; trajectory analysis with the fatigue inflection point and the at-fault creatives.

**Next step:&#x20;**&#x52;oute the at-fault creative IDs to your creative team with a "refresh by \[date]" note.

**3.3 The "did the platform change something" question**<br />
When to use it. A platform changed an algorithm or attribution window and you want to isolate the impact.

> 📘 Prompt
>
> \[Platform] \[reported / made an attribution change] on \[date]. Decompose<br />my \[platform] performance into change attributable to the platform<br />change vs change attributable to our actual marketing decisions over<br />that window.

**What you'll get back:&#x20;**&#x41; clean split of the variance into "us" and "them".

**Next step:&#x20;**&#x43;ommunicate the split internally so the team doesn't over-react to platform-side noise.

**3.4 The competitor pressure check**<br /><br />When to use it. CPCs spiked and you suspect a competitor entered the auction.

> 📘 Prompt
>
> In the last \[4 weeks], where did my CAC rise without a corresponding<br />change in our spend, bidding strategy, or creative? Are these signals<br />consistent with new competitive pressure in specific auctions?

**What you'll get back:&#x20;**&#x41; list of suspected competitive-pressure channels with confidence ratings.

Next step: Adjust bidding strategy on flagged auctions or shift budget to lower-pressure channels.<br />

***

## **4. Board / CFO prep**

The questions you need answered before the executive meeting.

**4.1 The board-ready iROAS summary**<br /><br />**When to use it:&#x20;**&#x59;ou're prepping the marketing slide for the board deck.

> 📘 Prompt.
>
> Draft a board-ready summary of last month's marketing performance using
> iROAS and incremental revenue (not platform-reported). Include channel
> mix, biggest mover, biggest concern, and a one-line methodology footnote
> my CFO can defend. Save it as a board prep note.

**What you'll get back:** A 3-paragraph summary plus a saved bookmark in your Lifesight workspace.

**Next step:&#x20;**&#x44;rop it straight into the board deck. Link the bookmark in speaker notes.

**4.2 The CFO "prove it" answer**<br /><br />**When to use it:&#x20;**&#x46;inance is challenging a marketing budget and wants a defensible number.

> 📘 Prompt
>
> For the last quarter, calculate the incremental revenue attributable
> to marketing, the implied iROAS, and the confidence interval. Compare
> to platform-reported ROAS so I can show the gap. Frame the response
> in P\&L language.

**What you'll get back:&#x20;**&#x41; finance-grade response: incremental revenue, iROAS, confidence interval, P\&L framing.

**Next step: &#x20;**&#x42;ring it to the CFO meeting. Save the response for repeat questions.

**4.3 The investor-update marketing line**<br /><br />**When to use it:&#x20;**&#x59;ou're contributing to an investor update.

> 📘 Prompt
>
> In two sentences, explain how marketing contributed to last quarter's
> revenue. Use causal numbers. Avoid jargon. Audience is non-marketing
> investors.

**What you'll get back:&#x20;**&#x54;wo clean sentences in the right register.

**Next step:** Hand to the IR team.

**4.4 The annual planning anchor**<br /><br />**When to use it:** It's planning season and you're setting next-year marketing budget.

> 📘 Prompt
>
> Based on the \[last X months] of causal data, what's the marketing<br />budget range that maximizes incremental revenue for next year?<br />Show me three scenarios: status quo, \[+X%}, and \[-X%}. For each,<br />project incremental revenue, blended iROAS, and the channels most<br />sensitive to the change.

**What you'll get back:** A three-scenario planning view.

**Next step:&#x20;**&#x54;ake into the planning meeting. Save as your annual planning anchor.<br />

***

## 5. Methodology lookup

Pull the receipts when someone asks "how do you know?"<br /><br />**5.1 Pull the holdout setup**<br /><br />When to use it. You're explaining a recent geo-lift test to finance or to a new team member.

> 📘 Prompt
>
> Find the holdout setup we used in the \[Q1 / most recent] geo test
> and summarize the methodology in language a non-marketer can follow.
> Include the markets, the test duration, and the confidence level.

**What you'll get back:&#x20;**&#x41; plain-English methodology summary pulled from your Lifesight knowledge base.

**Next step:&#x20;**&#x55;se it as the methodology slide in any deck that cites the test result.

**5.2 Reconcile two conflicting numbers**<br /><br />**When to use it:&#x20;**&#x54;wo reports show different numbers for the same channel and you need to know why.

> 📘 Prompt
>
> My \[report A] shows \[channel] at \[number]. My \[report B] shows the<br />same channel at \[different number]. Search the knowledge base for the<br />methodology difference between the two reports and explain in 3<br />bullets.

**What you'll get back:&#x20;**&#x41; bullet list reconciling the two methodologies.

**Next step:&#x20;**&#x53;end to the team that flagged the conflict. Update your reporting glossary if needed.

**5.3 Explain incrementality to your CFO**<br />
When to use it. Your CFO has asked (again) what "incrementality" actually means.

> 📘 Prompt
>
> Pull the Lifesight definition of incrementality and rewrite it as a
> 3-sentence explainer for a CFO who has never run a marketing
> experiment. End with the one sentence that distinguishes it from
> attribution.

**What you'll get back:** A CFO-grade definition with the attribution contrast at the end.

**Next step:&#x20;**&#x55;se it in your next finance review. Save it so you can hand it out next time.

**5.4 Audit-trail any number**<br />
When to use it. Someone needs to know exactly which model and run produced a number you cited.

> 📘 Prompt
>
> The number I just cited - \[paste number or describe the answer] -
> which model produced it, when was the model last run, and what's the
> confidence interval? Give me the audit-trail summary.

**What you'll get back:&#x20;**&#x4D;odel name, run timestamp, confidence interval, and the data window.

**Next step:&#x20;**&#x44;rop into any document or email that needs an audit trail.<br />

***

## 6. BFCM stress test

<br />Pressure-test your peak plan before the auction prices it for you.<br /><br />**6.1 The peak-week incrementality forecast**<br /><br />When to use it. 6 weeks before BFCM, finalizing the peak plan.

> 📘 Prompt
>
> For BFCM week, project incremental revenue and CAC for my current
> plan. Identify the 3 channels with the highest probability of
> saturation during peak. Recommend the spend cap that maximizes
> incremental revenue without crossing into negative incremental.

**What you'll get back:&#x20;**&#x46;orecast + saturation flags + recommended caps.

**Next step:&#x20;**&#x41;pply the caps. Save the forecast as your benchmark - re-run after BFCM to score the plan.

**6.2 The discount-depth simulator**<br /><br />**When to use it: &#x20;**&#x59;ou're choosing between three discount depths for the BFCM offer.

> 📘 Prompt.
>
> Simulate three BFCM offers on my live model: \[X%] sitewide,<br />\[X%] sitewide, and a tiered offer (BOGO on top SKUs, \[x%] on<br />everything else). Project incremental revenue, gross margin<br />impact, and post-BFCM repeat-rate effect for each.

**What you'll get back:&#x20;**&#x41; three-row comparison with the repeat-rate row often deciding the call.

**Next step: T**ake the comparison into the offer-selection meeting.

**6.3 The post-BFCM diagnostic**<br />
When to use it. First Monday after BFCM. Time to know what really happened.

> 📘 Prompt
>
> For BFCM week, calculate incremental revenue vs forecast for every
> channel. Identify the biggest positive and negative variance. For
> each, attribute the variance to (a) our decisions, (b) channel
> performance, or (c) market conditions. Save the diagnostic as a
> post-BFCM note.

**What you'll get back:&#x20;**&#x41; variance table with attribution split.

**Next step:&#x20;**&#x55;se the diagnostic in the post-mortem. Save it as the seed for next year's plan.

**6.4 The Q1 carryover read**<br />
When to use it. Second week of January. You need to know how much of Q4 is still working.

> 📘 Prompt
>
> Quantify the \[Quarter] brand investment carryover effect on\[Quarter] to date.<br />Which channels are still delivering incremental revenue from \[Quarter]<br />spend? What's the implied lifetime value of the BFCM-acquired cohort<br />vs the pre-Q4 baseline?

**What you'll get back:&#x20;**&#x43;arryover quantification by channel + LTV comparison.

**Next step:&#x20;**&#x55;se it to defend Q1 baseline spend. Save it for next year's Q4 planning anchor.

***

**A note on safety**<br /><br />Every prompt above is read-only against your causal model. None of them spend money or change a budget. Write actions - propose and apply budget reallocations - ship in Q3 with an explicit approval flow.

If you spot a prompt that should be here but isn't, email it to [product@lifesight.io](mailto:product@lifesight.io). The library updates monthly.
