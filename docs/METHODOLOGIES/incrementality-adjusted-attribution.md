---
title: Incrementality-adjusted Attribution
excerpt: What it is, why it matters, and how Lifesight implements it end‑to‑end.
deprecated: false
hidden: true
metadata:
  robots: index
---
Incrementality‑calibrated attribution reconciles your daily performance metrics with causal truth by adjusting platform/analytics reads using geo‑test lift and Causal MMM—so campaign‑level decisions align with what’s truly incremental, not just correlated.

At a glance

Answers: “What are the incremental conversions, revenue, and ROAS/CAC by channel/tactic/campaign today?”

Best for: Teams making weekly/daily budget, bidding, audience, and creative decisions that must align with finance and planning.

Inputs: Platform/analytics attribution, geo‑test lift, recent Causal MMM reads, taxonomy (Brand vs Non‑Brand, Prospecting vs Retargeting), standardized windows.

Outputs: Incrementality‑adjusted conversions/revenue, iROAS/CAC, deduplicated shares, and guardrail recommendations (caps/floors).

Privacy‑first: Works on aggregated data; no user‑level identifiers required.

Role alignment: Marketing uses granular, actionable KPIs; Finance sees totals that reconcile to causal evidence.

Read next: Geo‑based Incrementality Testing · Causal MMM · Quickstart: Calibrate attribution with incrementality

What it is (and isn’t)

What it is: A calibrated layer that takes the numbers you already operate on (platform, GA4, or internal MTA) and reweights credit using causal evidence—primarily geo tests and Causal MMM—to produce incremental KPIs at the channel/tactic/campaign level.

What it isn’t:

Not a replacement for planning models (MMM) or experiments; it inherits their truth.

Not a click‑path black box; we expose the mapping between evidence and adjustments.

Not identity‑dependent; it remains resilient to signal loss and cookie deprecation.

Why it matters

Stops the lower‑funnel death spiral: Retargeting and Brand Search often look best in raw reports but contribute least incrementally.

Funds true growth: Upper/mid‑funnel channels (CTV, YouTube, Prospecting) regain deserved credit when lift is proven.

Creates one truth from C‑suite to channel owners: Finance and marketing stop debating “whose numbers are right.”

How Lifesight calibrates attribution

1. Evidence hierarchy (what we trust, in order)

Recent geo‑test lift for the exact channel/tactic (gold standard).

Causal MMM incremental contribution and marginal effects for the same period.

Proxy inheritance from the closest proven tactic (e.g., channel‑level factor applied to similar campaigns) with a plan to test.

Conservative defaults only as a temporary bridge, flagged for validation.

We always record the source, date, and confidence of each adjustment.

2. Scope & taxonomy

Start at channel/tactic (e.g., Paid Search → Brand vs Non‑Brand; Paid Social → Prospecting vs Retargeting).

Roll down to campaign groups that share strategy once stability is demonstrated.

Keep labels consistent across MMM, tests, and attribution.

3. Windows & events alignment

Standardize lookback windows (e.g., 7‑day click, 1‑day view) and conversion event definitions.

Avoid mixing apples and oranges (e.g., comparing 28‑day view to 7‑day click).

Document chosen standards and apply them consistently.

4. Deduplication & guardrails

Enforce total‑to‑truth: adjusted conversions/revenue cannot exceed actual business outcomes.

Resolve double counting across platforms; dedupe at the channel/tactic level where overlap is known.

Apply floors/ceilings to prevent extreme whiplash from a single noisy test.

5. Publication & operations

Surface raw vs. adjusted side by side in dashboards so teams see the delta and rationale.

Feed adjusted KPIs into Optimize to set spending caps/floors and alerts.

Share an evidence log (what changed, why, and when) for auditability.

What gets adjusted (and how to read it)

Conversions & revenue: Reweighted to reflect incremental share by channel/tactic/campaign.

ROAS/CAC: Recomputed on the adjusted outcomes (iROAS, incremental CAC).

Share of credit: Rebalanced across channels so the pie matches causal truth.

Trends over time: Expect smoother, more stable patterns with fewer artificial spikes from platform modeling changes.

Expected patterns

Lower‑funnel harvesting (Retargeting, Brand Search): Adjusted down unless tests show incremental lift at current levels.

Upper/mid‑funnel (CTV, YouTube, Prospecting): Adjusted up when geo tests/MMM confirm causal impact.

Holistic effects: Some Search/Direct uplift will be attributed to proven awareness channels once calibrated.

Practical guidance (without UI steps)

Start narrow: Calibrate the biggest dollar decisions first (e.g., Retargeting caps, CTV scale).

Pilot visibility: Show raw vs adjusted for a month before enforcing guardrails—build trust.

Explain the “why”: Attach the test/MMM reference to every adjusted entity.

Keep windows consistent: Many “disagreements” are window mismatches, not method disagreements.

Revisit after promos: Big promotional windows can distort both raw and causal reads; schedule a post‑promo sanity pass.

Think portfolios, not heroes: Channels often work in combination; the goal is a balanced, incremental mix.

Calibration program cadence

After every decisive geo test: Refresh the affected factors.

Monthly: Sweep for drift; retire stale factors; reconcile to the latest MMM run.

Quarterly: Full review alongside MMM refresh and forecast re‑planning.

On change events: Major targeting or creative overhauls, new channel launches, or policy updates trigger a check.

Data you need (good → better → best)

Good: Platform/analytics attribution by channel/tactic, business outcomes (orders/revenue), standardized windows.

Better: Campaign groupings by strategy (Prospecting/Retargeting; Brand/Non‑Brand), creative or audience tags, geo splits.

Best: Recent geo‑test results, latest Causal MMM contributions and marginal curves, POS/retail roll‑ups for omnichannel brands.

Governance & versioning

Mapping table: Channel/tactic/campaign → evidence source → factor → effective dates.

Change log: Who changed what, when, and why; link to test/MMM artifacts.

Expiry policy: Factors older than a defined threshold (e.g., 90 days without reinforcement) are reviewed or rolled back.

Access & transparency: Make the evidence and change history visible to marketing, analytics, and finance.

Common pitfalls (and how to avoid them)

Over‑fitting to a single test: Corroborate with MMM or repeat the test before large budget shifts.

Taxonomy drift: If Brand/Non‑Brand or Prospecting/Retargeting aren’t aligned across systems, fix upstream before calibrating.

Window mismatches: Standardize lookbacks; otherwise “calibration” masks a measurement hygiene problem.

Adjusting too deep too fast: Campaign‑level factors without sufficient volume cause noise; stabilize at channel/tactic first.

Ignoring dedupe: Adjusted totals that exceed real sales erode trust—enforce total‑to‑truth.

Set‑and‑forget: Evidence decays; schedule refreshes and retire old factors.

FAQs

Does this replace MMM or experiments?
No. It operationalizes their truth for daily decisions. MMM + geo tests remain the sources of causal evidence.

Will adjusted numbers match platform dashboards?
Raw platform numbers remain visible, but adjusted KPIs become the optimization source of truth. Expect deltas—by design.

Can we still use multi‑touch attribution (MTA)?
Yes. Treat MTA as a granularity layer; then calibrate its totals to causal truth so its guidance becomes reliable.

What if different platforms claim the same conversion?
We dedupe and rebalance shares based on causal evidence to prevent double counting and inflated totals.

How do we explain changes to leadership?
Use the evidence log: “We ran test X / updated MMM Y; therefore, retargeting’s share is reduced by Z% and CTV’s increased by W%.”

Read next

Quickstart: Calibrate attribution with incrementality

Geo‑based Incrementality Testing

Causal MMM

Outcome Playbook: Maximize media efficiency

Product Guide: Optimize — Guardrails & caps
