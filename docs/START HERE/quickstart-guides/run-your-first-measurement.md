---
title: Run your first measurement read
excerpt: Baseline incrementality and marginal effects; interpret outputs; next actions.
deprecated: false
hidden: false
metadata:
  robots: index
---
Run a first Measure read to see what portion of results is truly incremental, which channels are saturating, and where the next dollar performs best—so you can act with confidence.

<br />

Audience: Performance & Media, Analytics & Insights, Marketing Ops
Goal: Produce a causally grounded baseline read (contribution, lift, and marginal returns) and turn it into immediate actions
Time: 45–90 minutes (assuming data is already connected)
Prerequisites: Completed “Connect your data” quickstart; at least 3–6 months of spend and outcome data across 2+ channels; workspace owner or editor
Outcomes: A saved Measure readout, a short list of “scale/cap/test” moves, and links to Forecast/Optimize

<br />

At a glance

<br />

You’ll get:

<br />

Incremental vs baseline contribution by channel/tactic

<br />

Marginal returns curves (where the next dollar works best)

<br />

Saturation flags and uncertainty bands

<br />

A shareable readout for marketing and finance

<br />

What matters most:

<br />

Clear KPI (orders, revenue, or subscriptions)

<br />

Clean, consistent channel mapping (brand vs non‑brand, prospecting vs retargeting where applicable)

<br />

Enough variation in spend over time (steady spend across all weeks reduces learning)

<br />

Step 1 — Create your Measure run

<br />

Select KPI: Choose the primary business outcome (e.g., Revenue or Orders/Subscribes).

<br />

Time aggregation: Start with weekly; move to daily only after your first baseline is stable.

<br />

Date range: Include at least 3–6 months of active spend with normal seasonality (exclude extreme anomalies if they distort learning).

<br />

Tip: If you have regions (e.g., states/DMAs) available, start national for speed; add geo layers in later runs to deepen insights.

<br />

Step 2 — Map channels, tactics, and context

<br />

Channel taxonomy: Map platforms to standardized channels (e.g., Paid Social, Paid Search, Video/CTV, Affiliate, Email).

<br />

For Search, split Brand vs Non‑Brand.

<br />

For Paid Social/Programmatic, tag Prospecting vs Retargeting if available.

<br />

Context variables: Add seasonality/holiday, promo/price flags, and any major site or retail events.

<br />

Sanity pass: Confirm there are no duplicate channels (e.g., Facebook and Meta as separate) and that spend isn’t zero for long stretches.

<br />

Why this matters: Clear splits (Brand vs Non‑Brand, Prospecting vs Retargeting) surface over‑credit and saturation you can act on immediately.

<br />

Step 3 — Use sensible modeling defaults

<br />

Effect timing: Keep default carryover/decay (adstock) settings for the first run.

<br />

Diminishing returns: Enable saturation so you can see marginal curves.

<br />

Relationships: If available, mark obvious causal constraints (e.g., forbid Retargeting → Baseline effects).

<br />

Calibration (optional): If you already ran a geo test, apply its lift to anchor the read; otherwise skip for this first pass.

<br />

First runs should be lightly constrained—you’ll refine settings as you learn and introduce calibration once tests complete.

<br />

Step 4 — Run the read and review the overview

<br />

Once the run completes, open Overview and note:

<br />

Incremental vs baseline: What portion of outcomes is driven by media vs base demand?

<br />

Channel contribution: Which channels/tactics contribute the largest incremental share?

<br />

Uncertainty bands: Wider bands suggest thin data or limited variation—note them for follow‑up.

<br />

Saturation signals: Which channels are close to or past the efficient frontier?

<br />

Save the run as “Baseline – Quarter/Date” so you have a stable reference for comparisons.

<br />

Step 5 — Interpret marginal returns (where to move the next $)

<br />

Open Marginal returns or Channel curves:

<br />

Steep and unsaturated → prime candidates to scale.

<br />

Flattening or saturated → candidates to cap or re‑route budget.

<br />

Surprisingly weak lower‑funnel (e.g., heavy Retargeting or Brand Search) → likely over‑credit; prioritize a geo test and near‑term caps.

<br />

Guidance: Use marginal curves, not average ROAS, to decide where the next dollar should go.

<br />

Step 6 — Draft your “scale/cap/test” moves (15 minutes)

<br />

Create a short list you can socialize today:

<br />

Scale: Channels with strong, steep marginal returns and room before saturation.

<br />

Cap: Channels with flattening curves or heavy overlap/harvesting (retargeting, brand search).

<br />

Test: Channels or tactics with high uncertainty or debate (e.g., CTV, YouTube, Influencer) → propose a geo test.

<br />

Calibrate: Where platform numbers diverge from incrementality, plan to apply lift factors in attribution.

<br />

Keep it practical: 3–5 moves with reason, expected impact direction, and guardrails.

<br />

Step 7 — Verify quality before sharing

<br />

Run these quick checks:

<br />

Face validity: Do big events (promos, holidays) reflect in the baseline vs media split?

<br />

Directionally consistent: Are channel rankings broadly reasonable vs. known performance, accounting for incrementality?

<br />

Coverage & recency: Latest full week present? Any big gaps in spend or outcomes?

<br />

Sensitivity (optional): Remove one channel and re‑run—do results behave plausibly?

<br />

If something looks off, revisit mapping (brand vs non‑brand; prospecting vs retargeting), date range, or context flags.

<br />

Step 8 — Share the readout

<br />

Executive summary (1 slide or short note): What’s incremental, top 3 moves, and known uncertainty.

<br />

Finance view: Contribution and marginal effects with ranges; note any planned calibration and tests.

<br />

Ops handoff: Translate moves into caps/floors and guardrails for channel teams.

<br />

Definition of done

<br />

A saved, named Measure read with contribution and marginal curves

<br />

A prioritized “scale/cap/test” list aligned to business goals

<br />

Stakeholders briefed; next actions assigned (tests, calibration, or re‑plan)

<br />

Common pitfalls (and quick fixes)

<br />

All channels look flat → Too little spend variation or overly short window. Fix: Extend date range; include promos/seasonality; confirm mapping.

<br />

Lower‑funnel looks “best” → Over‑credit from harvesting. Fix: Plan a geo test; introduce caps; apply calibration to attribution.

<br />

Wide uncertainty → Sparse data or too many fragments. Fix: Aggregate tactics, extend history, or add geo granularity if you have it.

<br />

Results fight intuition → Check for channel duplication, wrong currency/timezone, or missing large spend blocks.

<br />

What happens next

<br />

Launch a priority geo test to validate a debated channel and reduce uncertainty

<br />

Calibrate attribution so daily KPIs reflect causal truth

<br />

Move to Forecast to simulate profit‑aligned scenarios with the new curves

<br />

Set guardrails in Optimize to enforce caps/floors and pacing

<br />

Read next:

<br />

Quickstart: Launch a geo‑lift test

<br />

Quickstart: Calibrate attribution with incrementality

<br />

Quickstart: Build a forecast & plan

<br />

Measure — Interpreting incrementality & marginal returns

<br />

Causal Marketing Mix Modeling (Concepts)
