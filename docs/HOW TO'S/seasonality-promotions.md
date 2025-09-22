---
title: Seasonality & Promotions
excerpt: >-
  How to plan around peaks, quantify promo impact, and avoid over‑crediting
  media while protecting profit.
deprecated: false
hidden: true
metadata:
  robots: index
---
Seasonality and promotions change the baseline more than the media. This playbook shows how to separate promo‑driven demand from incremental media lift, forecast with uncertainty bands, and set guardrails so you hit targets without training customers to only buy on discount or overspending on harvesters.

At a glance

Use when: Entering peak periods (BFCM, back‑to‑school, holidays), running sitewide sales or bundles, launching new seasons, or coordinating retailer events.

You’ll achieve: A promo calendar with decision rules, a causal read on incremental vs baseline during promos, profit‑aware forecasts (p50/p10/p90), and a paced plan with caps/floors that prevent cannibalization and pull‑forward.

Core tools: Causal MMM (with promo/price variables) · Geo‑based Incrementality Testing (promo & media) · Incrementality‑calibrated Attribution · Ensemble Forecasting · Scenario Planner & Guardrails.

Audience, goal, and outcomes

Audience: CMO/VP Growth, Trade/Retail Marketing, CFO & FP&A, Performance & Media, Analytics & Insights
Goal: Maximize incremental, profitable revenue during seasonal/promo windows while protecting long‑term demand and brand equity.
Timeframe: 2–6 weeks planning; promo windows from days to weeks; debrief within 1–2 weeks after.
Outcomes:

Seasonality & promo calendar with objectives and decision rules

MMM with promo intensity and price factors; baseline vs media separation

Geo tests for offer/weighting with ≥80% power; lift readouts including pull‑forward/cannibalization

Risk‑aware forecast and an approved plan (p50/p10/p90)

Guardrails (brand/retargeting caps, prospecting floors, ramp/frequency limits) and a pacing worksheet

Post‑event readout with lessons, LTV effects, and updated rules

What “Seasonality & Promotions” really means (clear definitions)

Seasonality: Predictable, recurring patterns (holidays, weather, pay cycles) that raise/lower baseline demand even without media.

Promotion: A discount or offer that shifts conversion rate and pulls demand forward—often raising raw ROAS while reducing margin.

Incremental impact: Additional business value caused by media on top of seasonal/promo baseline, net of markdowns, returns, and cannibalization.

Pull‑forward: Sales during promo that replace purchases customers would have made later at full price.

Cannibalization: Sales that replace full‑price or organic performance, including brand search capture.

Step‑by‑step plan

1. Build the calendar & write the brief (Week −6 to −4)

Create a 1‑page Promo & Seasonality Brief for each event:

Window & intensity: Start/end dates; offer depth (% off); SKUs/collections; retailer windows.

Objective: Profit, revenue, CAC/payback; NTB % if acquisition‑led.

Decision rules: What constitutes success (e.g., “Proceed with deeper offers only if p50 profit ≥ target and p10 acceptable”).

Guardrails to enforce: Caps on harvesters; prospecting floors; ramp rates; frequency bands (video).

Testing plan: Which element to test (offer A/B, media weight, channel mix), where, and with what power.

2. Prepare data & hygiene (Week −5 to −3)

Promo tagging: Add promo flags, offer depth (% off), and category/SKU to your dataset; align to ISO weeks.

Price & margin: Provide variable margin and markdown cost so efficiency is profit‑aware.

Returns & cancellations: Document treatment by channel and product; align recognition timing.

Attribution windows: Standardize (e.g., 7‑day click, 1‑day view) before comparison; de‑dupe totals (total‑to‑truth).

3. Measure baseline vs media (Week −5 to −2)

Run a Measure read that includes:

Seasonality & holiday factors

Promo intensity (depth, # of promo days) and price variables

Retail/POS signals if omnichannel
Outputs: Incremental vs baseline split, marginal returns (mROAS) by channel/tactic for promo vs non‑promo periods, and early halo signals (e.g., CTV → Search/Direct).

4. Design promo & media tests (Week −4 to −1)

Use geo tests and/or staggered rollouts:

Offer depth A/B by region (20% vs 30%) to quantify margin trade‑off and pull‑forward.

Media weight tests (e.g., +30% YouTube/CTV vs BAU) during promo to isolate media‑on‑promo lift.

Brand Search & Retargeting caps in matched geos to measure over‑credit during promo spikes.

Retail Media: test category/competitive terms vs brand capture around retailer events; read total e‑comm + POS.

Design for ≥80% power, avoid asymmetric promos, and lock a freeze list (no mid‑test tinkering unless logged).

5. Forecast with bands; choose a plan (Week −2 to −1)

Use Ensemble Forecasting to create Efficiency, Balanced, Growth scenarios:

Inputs: MMM curves, promo/price variables, test anchors, incrementality‑adjusted KPIs, retail/stock constraints.

Outputs: p50/p10/p90 profit/revenue/CAC; weekly channel allocations; sensitivity drivers (e.g., promo response, CPM inflation).
Choose the scenario that wins on the objective at p50 and is acceptable at p10.

6. Execute with guardrails (During the window)

Caps: Retargeting share ≤X%; Brand Search impression share caps; exact‑match priority; negatives for cannibalization.

Floors: Maintain prospecting floors in proven channels (YouTube/CTV/Prospecting Social) to avoid starving future demand.

Ramp rates: ±20% WoW (or tighter) to prevent whiplash; pre‑approved exceptions logged.

Frequency discipline: Cap high‑freq cohorts in video; reinvest into reach bands (F1–2).

Inventory gating: Auto‑downweight SKUs with stock risk; block OOS creatives; coordinate with merchandising.

Retail windows: Respect retailer delivery/circular timing; avoid over‑spending outside shelf presence.

7. Monitor in‑flight; adjust inside guardrails

Daily health: Pacing vs plan, CPM/CPC inflation, frequency mix, brand/retargeting shares, inventory flags.

Variance calls: If outside p10/p90 for 2 consecutive days and guardrails allow a safe move, shift toward steep mROAS channels; otherwise hold and document.

8. Post‑promo readout & calibration (Week +1 to +2)

Incremental lift & profit net of markdowns and returns; pull‑forward ratio (post‑promo dip vs expected baseline).

Halo analysis: CTV/YouTube → Search/Direct; Retail Media → e‑comm/POS.

Calibration: Update MMM with promo/test anchors; refresh incrementality factors in attribution.

Rules update: Adjust caps/floors and offer playbook; decide whether deeper or longer promos are net accretive.

Channel‑level guidance during promo windows

Paid Search

Brand: Cap impression share; exact‑match first; use negatives to avoid organic cannibalization.

Non‑Brand: Target incremental query clusters; tighten negatives to prevent brand leakage.

Paid Social / Programmatic

Prospecting: Keep floors and diversify creative; manage frequency to maintain reach and avoid over‑serving bargain hunters.

Retargeting: Tighten recency; cap share—promo increases conversion rate, so raw ROAS spikes but incrementality usually falls.

YouTube / CTV

Use for pre‑heat (2–6 weeks out) and steady presence; control frequency; measure total lift (often realized in Search/Direct).

Retail Media

Test category/competitive terms; coordinate with retailer promos; watch for cannibalization of organic retail traffic.

Email/SMS

Avoid blast over‑sends; sequence to incremental cohorts; measure uplift vs holdout panels when possible.

Influencer/Affiliate

Track NTB share and coupon leakage; avoid last‑click hijacking; evaluate iCAC, not just code usage.

Guardrails library (copy, then tailor)

Retargeting cap: ≤ A% of paid conversions post‑calibration (tighter during promos).

Brand Search guardrail: Exact‑match priority; impression share cap; negatives for promo keywords that cannibalize.

Prospecting floor: ≥ B% of paid spend in proven reach channels during lead‑up and promo.

Frequency discipline: Cap high‑freq cohorts in video; reinvest in F1–2 reach.

Ramp rate: ± 20% WoW (or stricter for short promos).

Channel concentration: ≤ 40% in any single channel without CFO sign‑off.

Inventory gates: Auto‑pause creative/SKUs with low stock or long ship times.

Test blackout: No net‑new experiments within X days of marquee promo unless pre‑planned.

KPIs to run and report (incremental, not raw)

Incremental revenue & contribution profit (net of markdowns/returns)

iROAS / iCAC by channel/tactic; payback at p50 and p10

Pull‑forward ratio (post‑promo dip ÷ expected baseline)

Cannibalization ratio (brand/retargeting incremental ÷ reported)

Halo metrics (e.g., % of total lift captured in Search/Direct after CTV)

Forecast coverage (% of promo days within p10–p90)

NTB volume & share (for acquisition‑led promos)

Data requirements (good → better → best)

Good: Outcomes by day/week; promo flags and start/end; spend by channel; seasonality/holiday calendar.

Better: Offer depth (%), category/SKU tags, price/markdown, returns policy, geo splits, retail/POS for omnichannel, creative/audience tags.

Best: Inventory & distribution flags, retailer window/circular timing, share‑of‑search/brand interest, matched‑market test cells.

Industry notes

DTC & E‑commerce: Promo spikes make harvesters look great—cap them; protect Non‑Brand and upper‑funnel that seed demand pre‑event.

Retail & CPG: Include POS; plan around doors/distribution and trade spend; measure halo from media to retail sell‑through.

Consumer Services & Apps: Treat promos as pricing experiments; evaluate cohort LTV/payback and churn effects, not just week‑one revenue.

Common pitfalls (and how to avoid them)

Crediting media for promo effects → Include promo/price variables in MMM; test media weight changes to isolate media‑on‑promo lift.

Raw ROAS ≠ success → Use iROAS/iCAC and profit net of markdowns/returns.

Under‑powered tests → Lengthen window, add geo pairs, or increase spend delta; avoid asymmetric calendars.

Cannibalization blind spots → Cap Brand Search and Retargeting; measure net lift & post‑promo dip.

No pre‑heat → Start reach channels 2–6 weeks early; CPMs inflate near peaks—buy early, cap frequency.

Inventory miss → Block OOS SKUs; tie budgets to supply; coordinate merchandising.

Test creep → Freeze lists; log exceptions; otherwise your readout is noise.

30•60•90 plan (sample)

Days 1–30 (pre‑peak): Calendar & brief; data hygiene; Measure with promo variables; design geo tests (offer/weighting); pre‑heat upper‑funnel.

Days 31–60 (peak): Run tests; enforce caps/floors and frequency; monitor vs bands; adjust only within guardrails.

Days 61–90 (post): Readout with pull‑forward and halo; calibrate MMM & attribution; update rules; decide next promo depth/duration.

Templates & artifacts

Promo & Seasonality Brief (window, offer, objectives, rules)

Promo Calendar (events, retailer windows, creative plan)

Test Plan (offer depth or media weight; geos; power; decision rule)

Scenario & Pacing Worksheet (channel × week × constraints)

Post‑Promo Readout (incremental profit, pull‑forward, halo, lessons)

Guardrail Policy (caps/floors, frequency, ramp, inventory gates)

Read next

Methodology: Causal MMM

Methodology: Geo‑based Incrementality Testing

Methodology: Incrementality‑calibrated Attribution

Outcome Playbook: Forecast Profitable Growth

Quickstart: Build a forecast & plan
