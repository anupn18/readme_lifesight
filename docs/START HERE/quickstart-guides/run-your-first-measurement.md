---
title: Run your first measurement read
excerpt: Baseline incrementality and marginal effects; interpret outputs; next actions.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Run your first measurement read

Run a first Measure read to see what portion of results is truly incremental, which channels are saturating, and where the next dollar performs best—so you can act with confidence.

## Overview

*   **Audience:** Performance & Media, Analytics & Insights, Marketing Ops
*   **Goal:** Produce a causally grounded baseline read (contribution, lift, and marginal returns) and turn it into immediate actions
*   **Time:** 45–90 minutes (assuming data is already connected)
*   **Prerequisites:** Completed “Connect your data” quickstart; at least 3–6 months of spend and outcome data across 2+ channels; workspace owner or editor
*   **Outcomes:** A saved Measure readout, a short list of “scale/cap/test” moves, and links to Forecast/Optimize

## At a glance

You’ll get:

*   Incremental vs baseline contribution by channel/tactic
*   Marginal returns curves (where the next dollar works best)
*   Saturation flags and uncertainty bands
*   A shareable readout for marketing and finance

### What matters most:

*   Clear KPI (orders, revenue, or subscriptions)
*   Clean, consistent channel mapping (brand vs non‑brand, prospecting vs retargeting where applicable)
*   Enough variation in spend over time (steady spend across all weeks reduces learning)

## Step 1 — Create your Measure run

*   **Select KPI:** Choose the primary business outcome (e.g., Revenue or Orders/Subscribes).
*   **Time aggregation:** Start with weekly; move to daily only after your first baseline is stable.
*   **Date range:** Include at least 3–6 months of active spend with normal seasonality (exclude extreme anomalies if they distort learning).

**Tip:** If you have regions (e.g., states/DMAs) available, start national for speed; add geo layers in later runs to deepen insights.

## Step 2 — Map channels, tactics, and context

*   **Channel taxonomy:** Map platforms to standardized channels (e.g., Paid Social, Paid Search, Video/CTV, Affiliate, Email).
    *   For Search, split Brand vs Non‑Brand.
    *   For Paid Social/Programmatic, tag Prospecting vs Retargeting if available.
*   **Context variables:** Add seasonality/holiday, promo/price flags, and any major site or retail events.
*   **Sanity pass:** Confirm there are no duplicate channels (e.g., Facebook and Meta as separate) and that spend isn’t zero for long stretches.

**Why this matters:** Clear splits (Brand vs Non‑Brand, Prospecting vs Retargeting) surface over‑credit and saturation you can act on immediately.

## Step 3 — Use sensible modeling defaults

*   **Effect timing:** Keep default carryover/decay (adstock) settings for the first run.
*   **Diminishing returns:** Enable saturation so you can see marginal curves.
*   **Relationships:** If available, mark obvious causal constraints (e.g., forbid Retargeting → Baseline effects).
*   **Calibration (optional):** If you already ran a geo test, apply its lift to anchor the read; otherwise skip for this first pass.

First runs should be lightly constrained—you’ll refine settings as you learn and introduce calibration once tests complete.

## Step 4 — Run the read and review the overview

Once the run completes, open Overview and note:

*   **Incremental vs baseline:** What portion of outcomes is driven by media vs base demand?
*   **Channel contribution:** Which channels/tactics contribute the largest incremental share?
*   **Uncertainty bands:** Wider bands suggest thin data or limited variation—note them for follow‑up.
*   **Saturation signals:** Which channels are close to or past the efficient frontier?

Save the run as “Baseline – Quarter/Date” so you have a stable reference for comparisons.

## Step 5 — Interpret marginal returns (where to move the next $)

Open Marginal returns or Channel curves:

*   Steep and unsaturated → prime candidates to scale.
*   Flattening or saturated → candidates to cap or re‑route budget.
*   Surprisingly weak lower‑funnel (e.g., heavy Retargeting or Brand Search) → likely over‑credit; prioritize a geo test and near‑term caps.

**Guidance:** Use marginal curves, not average ROAS, to decide where the next dollar should go.

## Step 6 — Draft your “scale/cap/test” moves (15 minutes)

Create a short list you can socialize today:

*   **Scale:** Channels with strong, steep marginal returns and room before saturation.
*   **Cap:** Channels with flattening curves or heavy overlap/harvesting (retargeting, brand search).
*   **Test:** Channels or tactics with high uncertainty or debate (e.g., CTV, YouTube, Influencer) → propose a geo test.
*   **Calibrate:** Where platform numbers diverge from incrementality, plan to apply lift factors in attribution.

Keep it practical: 3–5 moves with reason, expected impact direction, and guardrails.

## Step 7 — Verify quality before sharing

Run these quick checks:

*   **Face validity:** Do big events (promos, holidays) reflect in the baseline vs media split?
*   **Directionally consistent:** Are channel rankings broadly reasonable vs. known performance, accounting for incrementality?
*   **Coverage & recency:** Latest full week present? Any big gaps in spend or outcomes?
*   **Sensitivity (optional):** Remove one channel and re‑run—do results behave plausibly?

If something looks off, revisit mapping (brand vs non‑brand; prospecting vs retargeting), date range, or context flags.

## Step 8 — Share the readout

*   **Executive summary (1 slide or short note):** What’s incremental, top 3 moves, and known uncertainty.
*   **Finance view:** Contribution and marginal effects with ranges; note any planned calibration and tests.
*   **Ops handoff:** Translate moves into caps/floors and guardrails for channel teams.

## Definition of done

*   A saved, named Measure read with contribution and marginal curves
*   A prioritized “scale/cap/test” list aligned to business goals
*   Stakeholders briefed; next actions assigned (tests, calibration, or re‑plan)

## Common pitfalls (and quick fixes)

*   **All channels look flat** → Too little spend variation or overly short window. **Fix:** Extend date range; include promos/seasonality; confirm mapping.
*   **Lower‑funnel looks “best”** → Over‑credit from harvesting. **Fix:** Plan a geo test; introduce caps; apply calibration to attribution.
*   **Wide uncertainty** → Sparse data or too many fragments. **Fix:** Aggregate tactics, extend history, or add geo granularity if you have it.
*   **Results fight intuition** → Check for channel duplication, wrong currency/timezone, or missing large spend blocks.

## What happens next

*   Launch a priority geo test to validate a debated channel and reduce uncertainty
*   Calibrate attribution so daily KPIs reflect causal truth
*   Move to Forecast to simulate profit‑aligned scenarios with the new curves
*   Set guardrails in Optimize to enforce caps/floors and pacing

## Read next:

*   [Quickstart: Launch a geo‑lift test](Quickstart: Launch a geo‑lift test)
*   [Quickstart: Calibrate attribution with incrementality](Quickstart: Calibrate attribution with incrementality)
*   [Quickstart: Build a forecast & plan](Quickstart: Build a forecast & plan)
*   [Measure — Interpreting incrementality & marginal returns](Measure — Interpreting incrementality & marginal returns)
*   [Causal Marketing Mix Modeling (Concepts)](Causal Marketing Mix Modeling (Concepts))
