---
title: MCP Prompt Library
excerpt: >-
  A copy-paste prompt library for using Lifesight MCP to answer planning,
  channel, anomaly, executive, methodology, and BFCM questions.
deprecated: false
hidden: false
metadata:
  title: Lifesight MCP Prompt Library
  description: >-
    A copy-paste prompt library for using Lifesight MCP to answer planning,
    channel, anomaly, executive, methodology, and BFCM questions.
  keywords:
    - Lifesight MCP Prompt Library
  robots: index
---
These prompts are organized by the decision you're trying to make, not the role you have. The ChatGPT examples below use the Lifesight tools available in ChatGPT. The results depend on your active workspace, data coverage, and permissions.

## How to use these prompts

Each prompt is paired with:

- **When to use it** - the trigger that should send you here.
- **The prompt** - copy as-is, or edit the bracketed slots.
- **What you'll get back** - the shape of Mia's answer.
- **What to do next** - the suggested follow-up.

**Tools the prompts call:**

- `list_mmm_models` - workspace inventory.

## ChatGPT examples

**Weekly readout**

> Give me a readout of last week's marketing performance in my current Lifesight workspace. Show incremental revenue and iROAS by channel, the biggest mover, and anything I should check before sharing it.

**Budget what-if**

> Using my current MMM model, compare my current budget allocation with a scenario that moves \[10%] of \[channel] spend to \[channel]. Show projected incremental revenue and iROAS for each.

**Channel saturation**

> Show the saturation curve for \[channel]. At what spend level do returns start to drop, and how far is current spend from that point?

**Data freshness**

> Check the data source health for my workspace. Which sources are stale or missing data, and which reports could that affect?

**Save then request promotion**

> Save the \[scenario] as a named plan called \[plan name]. Then request to make it the workspace default plan.

Saving a plan needs Write access. Requesting a change to the default plan needs Decide access, and a person approves or rejects the request in Lifesight.

## 1. Channel deep-dive

The decisions you have to make in the next eight weeks.

### 1.1 Where to move the next 20% of Q4 spend

**When to use it.** You're locking Q4 budget this week and want a defensible reallocation before the auction tightens.

> Stress-test my \[Quarter] plan. Where am I over-investing relative to incrementality, and what would moving \[%] of that spend to higher-iROAS channels look like in incremental revenue and CAC?

**What you'll get back:** A ranked table of over-invested channels with current iROAS, recommended deltas, and the projected incremental revenue lift. Methodology footnote underneath.

**Next step:** Paste the table into your Q4 plan doc. Summarize the findings and list the figures and dates I should cite in my notes.

### 1.2 The retargeting trap check

**When to use it.** Your team is defending a retargeting line item because the platform ROAS looks great.

> For my last \[weeks] of retargeting spend, show me platform-reported ROAS vs Lifesight iROAS by ad set. Flag every ad set where the gap is greater than 2x.

**What you'll get back:** Two-column comparison with gap highlighted. Mia adds a sentence on which retargeting audiences are most likely to be cannibalizing organic conversions.

**Next step:** Send the table to your media buyer with a "pause or cap?" tag on each flagged row.

### 1.3 The discount-or-brand decision

**When to use it.** Finance wants a discount; brand wants upper-funnel; you have to choose.

> Simulate two \[Quarter] scenarios on my live model: (A) repeat last year's \[%] sitewide discount, (B) hold price and shift the discount budget to upper-funnel video. Show incremental revenue, gross margin impact, and projected \[Quarter] carryover for each.

**What you'll get back:** A two-column scenario comparison with the carryover number isolated - this is usually the line that wins the argument.

**Next step:** Take both scenarios into the planning meeting. Save the answer so you can revisit it in February.

### 1.4 The Q1 cliff stress test

**When to use it:** You want to make sure your Q4 plan doesn't strand you in January.

> Based on my current \[Quarter] plan, project the \[Quarter] baseline assuming we cut upper-funnel investment by \[%] in week 1 of \[month]. Where does the revenue floor land? What's the brand-led investment in \[Quarter] that would raise that floor by \[%]?

**What you'll get back:** A projection chart description with two scenarios and a callout of the specific Q4 line items that drive the Q1 floor.

**Next step:** Use this as your Q1 insurance line in your Q4 board memo.

## 2. Channel diagnostics

When one channel is acting weird and you need to know if it's real.

### 2.1 The "why did this channel spike" question

**When to use it.** A channel jumped 30%+ week-over-week and you don't know if it's incremental or correlational.

> \[Channel] spend was up \[X]% last week and reported ROAS was up \[Y]%. What does my causal model say about the actual incremental change? Was the lift real, was it pulled from another channel, or was it correlation with \[seasonal event / promo]?

**What you'll get back:** A causal decomposition: incremental contribution, cannibalization from adjacent channels, and external-factor contribution.

**Next step:** If the lift is real, plan to test scaling. If it's cannibalization, flag the channel mix for review.

### 2.2 The cross-channel cannibalization map

**When to use it.** You want to know which of your "winning" channels are stealing credit from others.

> For my top \[5 channels] by spend, show me the cannibalization matrix: which channels are taking credit for conversions that other channels caused? Rank by total mis-credited revenue.

**What you'll get back:** A 5×5 matrix or ranked list. Most teams discover that 1-2 channels are credit-thieves and 1-2 are credit-victims.

**Next step:** Recalibrate channel-level KPIs to net of cannibalization. Save the matrix for the next attribution debate.

### 2.3 The "is this new channel ready to scale" question

**When to use it.** You're testing a new channel (CTV, retail media, podcasts) and need to decide whether to 5x it.

> For \[new channel], summarize the incremental contribution since launch. At what spend level does my causal model expect saturation to begin? What's the recommended next-quarter budget cap based on the saturation curve?

**What you'll get back:** A spend-vs-iROAS curve description, a saturation point, and a recommended cap.

**Next step:** Set the next-quarter cap below the saturation point. Plan a holdout test if confidence in the model is below 80%.

### 2.4 The channel deprecation check

**When to use it.** Before you kill a channel, make sure your platform numbers aren't hiding its real value.

> \[Channel] looks like an underperformer on platform ROAS. What does my causal model say about its true incremental contribution, including brand halo, view-through impact, and effect on downstream channels?

**What you'll get back:** True incremental contribution plus second-order effects on other channels.

**Next step:** If second-order effects are large, propose a 50% cut instead of a full kill. Save the analysis so you can re-test in 90 days.

## 3. Anomaly triage

Something looks off. Was it real or was it noise?

### 3.1 The morning anomaly check

**When to use it.** Slack lit up at 9am because a number moved.

> Find every channel where incremental contribution deviated more than 2 standard deviations from forecast in the last 7 days. For each, say whether the deviation crosses the threshold for action and what the recommended next step is.

**What you'll get back:** A short list of real anomalies, each tagged "act" or "noise" with reasoning.

**Next step:** Triage the "act" list with your team. Save the response as your morning briefing.

### 3.2 The campaign-level fatigue check

**When to use it.** Performance is degrading and you suspect creative fatigue.

> For \[campaign], show me incremental CPA week-over-week for the last \[8 weeks]. Identify when fatigue began and which creative cohorts are the primary contributors.

**What you'll get back:** A trajectory analysis with the fatigue inflection point and the at-fault creatives.

**Next step:** Route the at-fault creative IDs to your creative team with a "refresh by \[date]" note.

### 3.3 The "did the platform change something" question

**When to use it.** A platform changed an algorithm or attribution window and you want to isolate the impact.

> \[Platform] \[reported / made an attribution change] on \[date]. Decompose my \[platform] performance into change attributable to the platform change vs change attributable to our actual marketing decisions over that window.

**What you'll get back:** A clean split of the variance into "us" and "them".

**Next step:** Communicate the split internally so the team doesn't over-react to platform-side noise.

### 3.4 The competitor pressure check

**When to use it.** CPCs spiked and you suspect a competitor entered the auction.

> In the last \[4 weeks], where did my CAC rise without a corresponding change in our spend, bidding strategy, or creative? Are these signals consistent with new competitive pressure in specific auctions?

**What you'll get back:** A list of suspected competitive-pressure channels with confidence ratings.

**Next step:** Adjust bidding strategy on flagged auctions or shift budget to lower-pressure channels.

## 4. Board / CFO prep

The questions you need answered before the executive meeting.

### 4.1 The board-ready iROAS summary

**When to use it:** You're prepping the marketing slide for the board deck.

> Draft a board-ready summary of last month's marketing performance using iROAS and incremental revenue (not platform-reported). Include channel mix, biggest mover, biggest concern, and a one-line methodology footnote my CFO can defend. Summarize the findings and list the figures and dates I should cite in my notes.

**What you'll get back:** A 3-paragraph summary with the figures and dates to cite.

**Next step:** Drop it straight into the board deck. Paste the summary into your speaker notes.

### 4.2 The CFO "prove it" answer

**When to use it:** Finance is challenging a marketing budget and wants a defensible number.

> For the last quarter, calculate the incremental revenue attributable to marketing, the implied iROAS, and the confidence interval. Compare to platform-reported ROAS so I can show the gap. Frame the response in P\&L language.

**What you'll get back:** A finance-grade response: incremental revenue, iROAS, confidence interval, P\&L framing.

**Next step:** Bring it to the CFO meeting. Save the response for repeat questions.

### 4.3 The investor-update marketing line

**When to use it:** You're contributing to an investor update.

> In two sentences, explain how marketing contributed to last quarter's revenue. Use causal numbers. Avoid jargon. Audience is non-marketing investors.

**What you'll get back:** Two clean sentences in the right register.

**Next step:** Hand to the IR team.

### 4.4 The annual planning anchor

**When to use it:** It's planning season and you're setting next-year marketing budget.

> Based on the \[last X months] of causal data, what's the marketing budget range that maximizes incremental revenue for next year? Show me three scenarios: status quo, \[+X%\}, and \[-X%\}. For each, project incremental revenue, blended iROAS, and the channels most sensitive to the change.

**What you'll get back:** A three-scenario planning view.

**Next step:** Take into the planning meeting. Save as your annual planning anchor.

## 5. Methodology lookup

Pull the receipts when someone asks "how do you know?"

For methodology and metric definitions, use the Lifesight Help Center: \[Incrementality Testing], \[Geo-Testing], \[Marketing Mix Modelling].

### 5.1 Pull the holdout setup (Claude only)

**When to use it.** You're explaining a recent geo-lift test to finance or to a new team member.

> Find the holdout setup we used in the \[Q1 / most recent] geo test and summarize the methodology in language a non-marketer can follow. Include the markets, the test duration, and the confidence level.

**What you'll get back:** A plain-English methodology summary pulled from your Lifesight knowledge base.

**Next step:** Use it as the methodology slide in any deck that cites the test result.

### 5.2 Reconcile two conflicting numbers (Claude only)

**When to use it:** Two reports show different numbers for the same channel and you need to know why.

> My \[report A] shows \[channel] at \[number]. My \[report B] shows the same channel at \[different number]. Search the knowledge base for the methodology difference between the two reports and explain in 3 bullets.

**What you'll get back:** A bullet list reconciling the two methodologies.

**Next step:** Send to the team that flagged the conflict. Update your reporting glossary if needed.

### 5.3 Explain incrementality to your CFO (Claude only)

**When to use it.** Your CFO has asked (again) what "incrementality" actually means.

> Pull the Lifesight definition of incrementality and rewrite it as a 3-sentence explainer for a CFO who has never run a marketing experiment. End with the one sentence that distinguishes it from attribution.

**What you'll get back:** A CFO-grade definition with the attribution contrast at the end.

**Next step:** Use it in your next finance review. Save it so you can hand it out next time.

### 5.4 Audit-trail any number

**When to use it.** Someone needs to know exactly which model and run produced a number you cited.

> The number I just cited - \[paste number or describe the answer] - which model produced it, when was the model last run, and what's the confidence interval? Give me the audit-trail summary.

**What you'll get back:** Model name, run timestamp, confidence interval, and the data window.

**Next step:** Drop into any document or email that needs an audit trail.

## 6. BFCM stress test

Pressure-test your peak plan before the auction prices it for you.

### 6.1 The peak-week incrementality forecast

**When to use it.** 6 weeks before BFCM, finalizing the peak plan.

> For BFCM week, project incremental revenue and CAC for my current plan. Identify the 3 channels with the highest probability of saturation during peak. Recommend the spend cap that maximizes incremental revenue without crossing into negative incremental.

**What you'll get back:** Forecast + saturation flags + recommended caps.

**Next step:** Model the impact of these caps as a what-if. Re-run after BFCM to score the plan.

### 6.2 The discount-depth simulator

**When to use it:** You're choosing between three discount depths for the BFCM offer.

> Simulate three BFCM offers on my live model: \[X%] sitewide, \[X%] sitewide, and a tiered offer (BOGO on top SKUs, \[x%] on everything else). Project incremental revenue, gross margin impact, and post-BFCM repeat-rate effect for each.

**What you'll get back:** A three-row comparison with the repeat-rate row often deciding the call.

**Next step:** Take the comparison into the offer-selection meeting.

### 6.3 The post-BFCM diagnostic

**When to use it.** First Monday after BFCM. Time to know what really happened.

> For BFCM week, calculate incremental revenue vs forecast for every channel. Identify the biggest positive and negative variance. For each, attribute the variance to (a) our decisions, (b) channel performance, or (c) market conditions. Summarize the findings and the checks I should record.

**What you'll get back:** A variance table with attribution split.

**Next step:** Use the diagnostic in the post-mortem. Use it as the starting point for next year's plan.

### 6.4 The Q1 carryover read

**When to use it.** Second week of January. You need to know how much of Q4 is still working.

> Quantify the \[Quarter] brand investment carryover effect on\[Quarter] to date. Which channels are still delivering incremental revenue from \[Quarter] spend? What's the implied lifetime value of the BFCM-acquired cohort vs the pre-Q4 baseline?

**What you'll get back:** Carryover quantification by channel + LTV comparison.

**Next step:** Use it to defend Q1 baseline spend. Save it for next year's Q4 planning anchor.

## A note on safety

Lifesight applies your workspace permissions. What-if planning can create temporary scenarios. Saving a named plan leaves the existing default in place. Changing the workspace default requires a separate proposal and approval in Lifesight.

If you spot a prompt that should be here but isn't, email it to [product@lifesight.io](mailto:product@lifesight.io). The library updates monthly.

***

**What changed this time:**

- **Prompts 5.1 to 5.3 are back.** Each is labeled "(Claude only)", which is the artifact's option for keeping them. The Help Center line goes at the top of section 5, and 5.4 keeps its number.
- **My extra edits are undone.** That covers the "24 prompts" line, the "Mia" mentions and the typos in 4.4 and 6.4. Those now read as they do on the live page.
- **The section 2 rename stays.** The artifact flags it as a fix worth making in the same pass.

**Two things to check before you publish:**

1. **The five ChatGPT example prompts are my drafts.** The artifact points to five prompts in the original edits file, but that file isn't in the artifact. If you have it, swap in its wording.
2. **The three Help Center names in section 5 need links** to the matching pages.
