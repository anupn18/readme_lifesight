---
title: Forecast
excerpt: How to forecast to achieve profit and growth
deprecated: false
hidden: false
metadata:
  robots: index
---
Forecast turns your latest causal evidence into risk‑aware scenarios—with p50/p10/p90 ranges—so you can choose a profit‑aligned plan, pace it by week, and operate with clear guardrails.

At a glance

Purpose: Approve a plan that meets profit, revenue, or payback targets under uncertainty, not just on point estimates.

Who it’s for: CMO/VP Growth, CFO & FP&A, Performance & Media, Analytics & Insights.

Decisions you’ll make:

Which scenario to approve (Efficiency · Balanced · Growth)

How to allocate spend by channel/week within real‑world constraints

What guardrails to enforce (floors/ceilings, ramp rates, frequency, concentration caps)

Primary outputs:

p50/p10/p90 forecasts for the chosen objective

Channel × week pacing plan with notes on ramps and ceilings hit

Sensitivity drivers (what moves outcomes most) and re‑plan triggers

Works with: Measure (marginal curves) · Optimize (enforcement) · Analyze (dashboards) · Methodologies (Ensemble Forecasting, MMM, Geo Tests, Calibrated Attribution).

What Forecast includes

Scenario Builder
Set the objective (Profit/Revenue/CAC‑Payback), horizon (4–12 weeks typical), base period for comparisons, and the budget envelope.

Constraints & Guardrails
Encode reality: channel floors/ceilings, ramp‑rate limits, geo/retail windows, inventory/distribution flags, promo calendar, and business rules (e.g., retargeting cap, brand search guardrails, channel concentration limit).

Evidence Loader
Pull in MMM curves (marginal returns & saturation), geo‑test lift anchors, incrementality‑adjusted KPIs for near‑term pulse, and context drivers (seasonality, price/promo, POS).

Ensemble Forecast Engine
Produces probabilistic forecasts (p50/p10/p90) by scenario and a sensitivity view highlighting which assumptions (e.g., media response, promo intensity) drive risk.

Scenario Compare & Choose
Side‑by‑side scorecard by objective, downside resilience (p10), feasibility (ramps, capacity), and finance alignment—then one‑click mark as Approved Plan.

Pacing & Governance
Export channel × week spend, caps/floors, and alerts. Define re‑plan triggers and change‑control rules; version everything.

How Forecast works (high level)

Ensemble forecasting blends four inputs: MMM response curves (for next‑dollar effects), base‑demand time‑series (trend/seasonality/promo), experiment‑anchored uplift (geo tests), and incrementality‑adjusted operational signals.

Uncertainty propagation simulates plausible ranges on media response, promo intensity, conversion, and demand to generate p50/p10/p90 bands.

Risk scoring favors scenarios that meet your objective at p50 and remain acceptable at p10.

Deep dive: Methodology → Ensemble Forecasting

Typical workflows
Quarterly planning (most common)

Load latest Measure run and geo‑test anchors.

Build Efficiency, Balanced, Growth scenarios.

Compare p50/p10/p90, pick the plan, export pacing, and publish guardrails.

Monthly re‑plan

Review realized vs forecast variance; if outside bands or assumptions changed (promo, supply, policy), adjust constraints and re‑run. Small reallocations keep you on track without a full refresh.

Pre‑peak / promotion planning

Add promo/price variables and inventory/retail windows. Expect raw platform ROAS to spike; Forecast keeps incrementality and profit honest.

New channel ramp

After a pilot geo test, anchor curves and generate a step‑up ramp with floors/caps so the new spend scales responsibly.

Interpreting Forecast outputs

Outcomes panel: p50 (most likely), p10/p90 (downside/upside) for your chosen objective, plus revenue, profit, CAC/payback.

Spend plan: Channel × week allocations, ramp notes, constraints hit (ceilings, floors, concentration).

Top moves: Net budget shifts and why (steep mROAS, proven lift, saturation elsewhere).

Sensitivity drivers: Which assumptions dominate risk (e.g., promo response, CPM inflation). Use these to target tests or contingency plans.

Rule of thumb: Approve the scenario that wins at p50 and is acceptable at p10 given your risk tolerance and cash cycle.

Decision recipes (ready to use)

Choose a plan: If Profit is the objective, prefer the scenario with highest p50 profit and p10 above the guardrail; record a one‑line rationale.

Allocate marginal dollars: Move budget toward channels with steep mROAS and headroom; pull from flat regions nearing saturation.

Set guardrails:

Retargeting cap and Brand Search guardrail to prevent cannibalization.

Prospecting floors in proven upper/mid‑funnel (YouTube/CTV/Social).

Ramp‑rate limits (e.g., ±20% WoW) and channel concentration caps (e.g., ≤40% in one channel).

Trigger a re‑plan: Breach p10 bands two weeks running; major supply/policy shock; creative overhaul; decisive new test read‑out.

Data requirements & mapping

Minimum viable

Outcomes (orders/revenue/subscriptions) weekly; channel spend; seasonality/holiday calendar.

Better

Price/promo calendar and intensity; geo splits; POS/retail roll‑ups; incrementality‑adjusted KPIs; creative/audience tags.

Best

Latest MMM curves by channel/tactic; recent geo‑test results; inventory/distribution flags; macro/competitive proxies (share of search).

Mapping guidelines

One timezone, one currency, aligned ISO weeks.

Standard splits: Brand vs Non‑Brand (Search), Prospecting vs Retargeting (Social/Programmatic).

Deduplicate conversions: total‑to‑truth—adjusted totals never exceed actuals.

Governance, refresh & versioning

Cadence: Quarterly full refresh; monthly light re‑plans; off‑cycle re‑plan on trigger.

Sign‑offs: CMO/Growth proposes; CMO + CFO approve; Channel owners implement; FP&A audits.

Versioning: Store scenario inputs, constraints, weights, and rationale.

Variance analysis: Each week, explain realized vs forecast gaps; log causes (auction shifts, promos, inventory) and corrective actions.

Permissions & roles (suggested)

Admin/Owner: Workspace settings, fiscal/calendar alignment.

Analytics & Insights: Evidence loader, scenario setup, risk analysis.

CMO/VP Growth: Scenario selection, guardrails approval.

CFO & FP&A: Objective choice, profit/payback validation, sign‑off.

Performance & Media: Execute pacing and guardrails; feed back feasibility constraints.

Exports & hand‑offs

Pacing worksheet: Channel × week spend, ramps, and notes—handed to channel owners.

Guardrail pack: Caps/floors, ramp limits, frequency rules, concentration caps, and alert thresholds.

Finance pack: Plan summary (objective, p50/p10/p90, top moves, risks), contribution profit and payback mapping.

Evidence log: What changed (new tests, curve updates), when, and why.

Troubleshooting

Scenario looks too “perfect”: You’re optimizing to average ROAS. Turn on marginal curves and saturation; add ceilings.

Bands are very wide: Evidence is thin or volatile—extend history, add geo granularity, or run a targeted test to reduce uncertainty.

Ramps aren’t feasible: Add ramp‑rate and creative capacity constraints; lock geo/retail windows.

Retail plan misses reality: Include distribution/doors and inventory gates; sync to retailer calendars.

Results diverge from ops: Ensure calibrated attribution is live; re‑run after major calibration updates.

FAQs

Profit vs Revenue vs CAC—how do we choose?
Pick one per cycle, based on strategy and cash needs. Profit is the default; Revenue when share or top‑line growth is paramount; CAC/Payback when cash cycle and LTV thresholds dominate.

How often do we refresh?
Quarterly by default; monthly re‑plans as evidence or conditions change; immediately after decisive geo tests.

Can we plan with a brand‑new channel?
Yes—anchor with pilot geo‑test lift, use conservative curves, and scale through a step‑up ramp with floors/caps.

Is this Finance’s “official” forecast?
It’s the marketing‑sourced, causally calibrated forecast. FP&A aligns it to P&L via agreed assumptions and signs off in the scenario compare step.

Why p50/p10/p90?
Because markets move. Bands communicate risk honestly and prevent over‑committing to point optimism.

What “good” looks like

Plan approved with explicit trade‑offs and CFO sign‑off.

Variance within bands most weeks; outliers explained early.

Budget mix shifts toward channels with proven lift and headroom; harvesters capped.

Faster re‑plans using the same rules—no methodology debates.

Clear linkage from plan to Optimize guardrails and Analyze dashboards.

Related content

Quickstart: Build a forecast & plan

Methodology: Ensemble Forecasting · Causal MMM · Geo‑based Incrementality Testing · Incrementality‑calibrated Attribution

Product Guides: Measure · Optimize · Analyze

Outcome Playbooks: Forecast Profitable Growth · Maximize Media Efficiency · Align Marketing & Finance Teams
