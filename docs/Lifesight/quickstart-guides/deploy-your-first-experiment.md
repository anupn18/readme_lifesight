---
title: Deploy your first experiment
excerpt: Test vs control, power, timing; read‑out expectations; common pitfalls.
deprecated: false
hidden: true
link:
  new_tab: false
metadata:
  robots: index
---
Launch a geo-lift test to prove causal impact of a channel, tactic, audience, or offer—so you can scale winners, cap over-credited spend, and calibrate both planning and daily KPIs.

## Audience & Goals

* **Audience:** Performance & Media, Analytics & Insights, Marketing Ops
* **Goal:** Design and run a statistically reliable geo test that returns a decision-grade lift readout
* **Time to set up:** 60–90 minutes (run time typically 2–6 weeks, depending on volume and noise)
* **Prerequisites:** Connected outcomes + media data; stable campaign setup; ability to target by geo (DMA/State/City)
* **Outcomes:** Approved test plan with matched markets, monitoring guardrails, and a scheduled read-out that feeds calibration

## At a Glance

* **When to use:** You need causal proof for a debated channel (e.g., CTV, YouTube, Prospecting) or to right-size lower-funnel (e.g., Retargeting, Brand Search).
* **What you’ll get:** Incremental lift, incremental revenue, and decision guidance (scale/cap/hold), plus factors to calibrate MMM and attribution.
* **Typical test types:**
  * **Holdout:** Pause/limit in test geos; control runs as usual.
  * **Scale-up:** Increase spend in test geos vs. business-as-usual control geos.
* **Target reliability:** Design for ≥80% power to detect a meaningful lift (your Minimum Detectable Effect, or MDE).
* **Avoid:** Major holidays, heavy promos, or site changes that differ across geos.

## Step 1 — Define the decision and KPI

* **Primary decision:** What will you do if lift is positive/neutral/negative? (e.g., “Scale CTV by +20% across Tier-1 DMAs if lift ≥X.”)
* **Primary KPI:** Choose one—Revenue, Orders, Subscribers—with a consistent attribution of conversions to geo (e.g., shipping address, billing zip).
* **MDE & power:** Agree on a lift magnitude worth detecting and target ≥80% power in the design.
* **Test type:**
  * Holdout if you can safely pause/limit in certain geos.
  * Scale-up if you can’t pause but can add incremental spend cleanly.
* Document “if-then” actions now. A test without a pre-committed decision rule invites debate later.

## Step 2 — Select eligible geos and build matched pairs

* **Candidate pool:** Start with geos that you can target and that have clean sales mapping (DMAs/States/Cities).
* **Exclusions:** Remove geos with unusual supply constraints, heavy retail overlaps, or cross-border bleed (tourism hubs).
* **Matching:** Pair geos on pre-period similarity (size, seasonality, channel mix, and baseline sales), then assign one of each pair to test and control.
* **Buffers:** Exclude postal codes that straddle borders to reduce spillover.
* **Count:** Aim for multiple pairs rather than a single large pair—redundancy improves reliability.

## Step 3 — Size & schedule the test

* **Duration:** Plan for 2–6 weeks depending on volume and variability; longer windows reduce noise.
* **Budget delta:**
  * **Scale-up:** Add a clear, consistent incremental spend (e.g., +30% vs. baseline) in test geos.
  * **Holdout:** Reduce/pause the focal tactic in test geos while holding other channels steady.
* **Calendar:** Avoid major holidays or promos unless applied symmetrically to test and control.
* **Freeze list:** Keep creative, bids, audiences, and flighting constant except for the planned change.

## Step 4 — Trafficking plan & guardrails

* **Geo lists:** Create and lock named geo sets for test and control (share IDs with all buyers).
* **Campaign structure:** Duplicate or segment campaigns so test/control spend is isolated and auditable.
* **Pacing guardrails:** Daily/weekly pacing checks with acceptable variance bands (e.g., ±10%).
* **Change control:** A simple rule: no mid-test optimizations beyond critical fixes (site outage, policy violation). Log everything.

## Step 5 — Pre-launch validation (24–72 hours before start)

* **Pre-period balance:** Verify test vs. control are parallel on baseline KPIs.
* **Pixel/analytics health:** Confirm conversion streams are landing and mapped to the correct geo.
* **Inventory / promo parity:** Ensure no one-off events will hit only one side.
* **Final sign-off:** CMO/Growth and Finance agree on success criteria and the decision rule.

## Step 6 — Live monitoring (during the test)

* **Daily health checks:** Pacing vs. plan, spend delta holding, no spillover targeting enabled.
* **Ops alerts:** Detect sudden creative rotations or budget throttles; correct only if they break the test design.
* **Anomaly log:** Note external events (weather, outages) that might explain outliers.
* Stay the course. Frequent mid-test tinkering is the #1 cause of inconclusive results.

## Step 7 — Read-out & validation

When the test window ends:

* **Compliance audit:** Confirm the planned budget delta or holdout actually occurred and that control stayed as designed.
* **Balance checks:** Re-check pre-period parity and within-test anomalies.
* **Lift read-out:** Produce the incremental impact (direction and magnitude) with uncertainty ranges and a simple decision rubric:
  * Scale (lift positive and decision-grade)
  * Maintain (neutral/uncertain; rerun with more power)
  * Reduce/Stop (lift negative or poor efficiency)
* **Heterogeneity:** Note which geos or segments responded best; this informs targeting and future tests.
* **Story for finance:** Convert lift to incremental revenue and efficiency; state the confidence of the result and any caveats.

## Step 8 — Calibrate planning & daily KPIs

* **MMM calibration:** Feed the measured lift into your model as a constraint/anchor for the tested tactic.
* **Attribution calibration:** Apply incrementality factors so platform and analytics KPIs reflect causal truth day-to-day.
* **Guardrails:** Update caps/floors for lower-funnel tactics (e.g., Retargeting, Brand Search) based on test evidence.

## Definition of done

* Signed test plan with geos, test type, KPI, duration, and decision rule
* Live test with monitoring and change log
* Read-out delivered with a clear scale/cap/maintain recommendation
* Calibration applied to MMM and attribution; guardrails updated
* Follow-up test (if needed) added to the learning agenda

## Common pitfalls (and how to avoid them)

* **Inadequate power / too short** → Extend duration or add more geo pairs; increase budget delta for scale-ups.
* **Spillover contamination** → Tighten geo lists, add buffer zips, avoid radius targeting that bleeds.
* **Mid-test optimizations** → Freeze creative/audiences; document exceptions; re-start clock if design breaks.
* **Calendar shocks** → Avoid promo periods, or mirror them in both arms; log any asymmetries.
* **No decision rule** → Pre-commit “if-then” actions; otherwise results stall in debate.
* **Bad geo mapping of conversions** → Use reliable location fields (e.g., shipping address), and keep the same mapping pre/during/post test.

## Templates & artifacts

* Geo test plan template (objectives, geos, KPI, type, duration, decision rule)
* Matched-markets workbook (candidate geos, balancing metrics, assignments)
* Run-of-show checklist (pre-launch, in-flight checks, read-out)
* Change log (single source of truth for any deviations)

## What happens next

* Calibrate attribution so your daily optimization reflects the measured lift
* Re-plan budgets in Forecast using the updated evidence
* Queue the next test (e.g., creative strategy, offer, or a different channel) to keep improving power and precision

## Read next:

* Quickstart: Calibrate attribution with incrementality
* Quickstart: Build a forecast & plan
* Methodology: Geo-based Incrementality Testing
* Outcome Playbook: Prove incremental ROI
