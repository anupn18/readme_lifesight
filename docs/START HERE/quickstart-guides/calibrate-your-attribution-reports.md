---
title: Calibrate your attribution reports
excerpt: Apply lift factors; align daily KPIs to causal truth.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
# Calibrate Your Attribution Reports

Apply lift factors; align daily KPIs to causal truth.

Calibrate your day-to-day attribution so channel and campaign KPIs reflect incremental impact—not just correlation. You’ll map lift from geo tests and evidence from Measure into incrementality-adjusted reads that guide real budgeting and bidding.

**Audience:** Performance & Media, Analytics & Insights

**Goal:** Produce incrementality-adjusted KPIs that reconcile with causal truth

**Time:** 45–90 minutes (assuming Measure and/or a recent geo test are complete)

**Prerequisites:** “Connect your data” and “Run your first Measure read”; ideally one recent geo-lift test for a debated tactic

**Outcomes:** A documented calibration plan, adjusted channel/campaign KPIs, and a rollout/gov cadence

## At a glance

*   **When to use:** Platform/MTA metrics over-credit lower-funnel (e.g., Retargeting, Brand Search) or under-credit upper-funnel (e.g., CTV, YouTube).
*   **What you’ll get:** Adjusted conversions, revenue, ROAS/CAC, and share that match incremental reality day-to-day.
*   **What you need:** Lift from a recent geo test (best) and your latest Measure read (marginal/total effects).

## Step 1 — Define scope and baseline

*   **Scope of calibration:** Choose the entities to adjust (start at channel or tactic; extend to campaign later).
*   **Baseline model:** Decide which raw read you’re calibrating (e.g., platform-reported or analytics attribution).
*   **Windows & events:** Standardize lookback windows and the conversion event you’ll use for calibration so like-for-like comparisons hold.
*   **Success criteria:** Document what “good” looks like (e.g., adjusted totals reconcile with causal evidence within a defined range).

*Keep scope tight for the first pass: e.g., Brand Search, Retargeting, CTV/YouTube Prospecting.*

## Step 2 — Gather causal evidence

*   **Geo-lift tests:** Pull the latest read-outs for the in-scope channels/tactics. Note the direction, magnitude, and confidence.
*   **Measure read:** Use your Measure overview to understand incremental contribution and marginal effects by channel/tactic.
*   **Quality notes:** Flag any known caveats (e.g., noisy weeks, promos) that should temper how aggressively you calibrate.

## Step 3 — Map evidence to attribution entities

*   **Align taxonomy:** Ensure the channels/tactics in attribution match the labels used in tests and Measure (e.g., Brand vs Non-Brand, Prospecting vs Retargeting).
*   **Create a mapping table:** For each channel/tactic in scope, record the evidence source (test/Measure), time coverage, and intended adjustment (increase/decrease credit).
*   **Coverage decision:** If a tactic lacks direct test evidence, inherit from the nearest proven proxy (e.g., apply channel-level factor to similar campaigns) and mark it for a future test.

## Step 4 — Apply incrementality adjustments

*   **Channel/tactic level first:** Adjust reported conversions/revenue so that each in-scope entity reflects measured incremental impact.

**Guardrails:**

*   Do not let adjusted totals exceed actual sales for the period.
*   Keep an eye on share shifts—large swings should be explainable by the evidence.

*   **Granularity rollout:** Once channel/tactic adjustments look stable, push down to campaign groupings that share the same strategy (e.g., Prospecting vs Retargeting sets).

*This pass creates incrementality-adjusted KPIs your teams will use daily: adjusted conversions/revenue, iROAS, and incremental CAC.*

## Step 5 — Reconcile and sanity-check

*   **Topline reconcile:** Aggregated adjusted results should align with Measure and recent test evidence within your agreed range.
*   **Directionality:** Lower-funnel tactics (Brand Search/Retargeting) often drop; upper-funnel (CTV/YouTube/Prospecting) often gain—confirm the story makes sense.
*   **Time stability:** Spot-check 2–3 recent weeks to ensure adjustments behave plausibly across time (not just a single week).

## Step 6 — Publish and operationalize

*   **Dashboards:** Surface incrementality-adjusted metrics alongside raw platform reads so teams see both and understand the delta.
*   **Playbooks:** Document how to use adjusted KPIs for scaling, capping, and creative/audience testing.
*   **Guardrails:** Update caps/floors for tactics that are over-credited in raw reads (e.g., set a retargeting ceiling).
*   **Change log:** Record the calibration version, evidence sources, and in-scope entities for auditability.

## Step 7 — Set cadence & ownership

*   **Refresh:** Revisit calibration monthly or after every major geo test.
*   **Owners:** Analytics (method) + Performance (activation) co-own; Finance reviews for P&L alignment.
*   **Learning agenda:** Queue tests for any high-spend tactics still running on inherited/proxy adjustments.

## Definition of done

*   A clearly scoped calibration plan with in-scope channels/tactics
*   Adjusted KPIs that reconcile with causal evidence within your accepted range
*   Dashboards updated; playbook and guardrails published
*   Ownership and refresh cadence documented

## Common pitfalls (and how to avoid them)

*   **Over-fitting to one test:** Use multiple evidence sources or re-test before making extreme shifts.
*   **Mismatched taxonomy:** If your Brand/Non-Brand or Prospecting/Retargeting splits don’t align across systems, fixes upstream first.
*   **Unrealistic totals:** If adjusted conversions exceed actual sales, review inheritance choices and guardrails.
*   **Frozen calibration:** Evidence evolves—schedule refreshes and retire old factors as new tests land.

## Templates & artifacts

*   Calibration mapping table (entity ⇄ evidence ⇄ adjustment)
*   Before/after dashboard view (raw vs incrementality-adjusted)
*   Guardrail policy (caps/floors for over-credited tactics)
*   Calibration change log (version, date, owner, notes)

## What happens next

*   **Move to Forecast:** Use the now-realistic contribution and marginal effects to plan profit-aligned budgets.
*   **Enforce in Optimize:** Translate adjusted KPIs into caps/floors and pacing rules.
*   **Test the gaps:** Launch geo tests for high-spend tactics still running on proxy adjustments.

## Read next

*   Quickstart: Build a forecast & plan
*   Optimize — Guardrails & caps
*   Methodology: Incrementality-calibrated Attribution
*   Outcome Playbook: Maximize media efficiency