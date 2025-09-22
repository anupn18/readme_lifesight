---
title: Optimize
excerpt: How to optimize channel and campaign spend
deprecated: false
hidden: false
metadata:
  robots: index
---
Optimize turns causal evidence into daily, enforceable actions—budget shifts, caps/floors, ramp‑rate limits, and alerts—so your teams spend each marginal dollar where it’s incremental, not just where platform ROAS looks good.

At a glance

Purpose: Operationalize your approved plan with guardrails and incrementality‑adjusted KPIs, then course‑correct quickly when reality shifts.

Who it’s for: Performance & Media, Growth/Acquisition, Analytics & Insights, CMO/VP Growth, CFO & FP&A.

Decisions you’ll make:

Accept or edit budget shift recommendations by channel/tactic/campaign

Set and enforce caps/floors, ramp‑rates, frequency and concentration limits

Trigger re‑plans when results breach risk bands or assumptions change

Primary outputs:

Daily/weekly recommendations ranked by incremental impact and confidence

Guardrail policy (caps/floors, ramps, frequency, concentration) with breach alerts

Pacing view against the approved plan and variance explanations

Works with: Measure (marginal curves), Forecast (approved scenario and bands), Analyze (dashboards), and Methodologies (Geo Tests, Causal MMM, Incrementality‑calibrated Attribution).

What Optimize includes

Recommendation Center

Ranked Scale / Cap / Shift suggestions with expected incremental impact, rationale (curve position, lift evidence), and confidence ranges.

Filters by objective (profit, revenue, CAC/payback), channel/tactic, and risk level.

Guardrails & Policy Engine

Caps/Floors (e.g., retargeting ≤X%, prospecting ≥Y%).

Ramp‑rates (e.g., ±20% WoW per channel).

Channel concentration limits (e.g., ≤40% in any single channel).

Brand Search guardrails (exact‑match priority, impression‑share cap, negatives).

Frequency discipline for upper‑funnel (cap high‑freq cohorts; prioritize F1–2 reach).

Pacing Orchestrator

Channel × week pacing vs the Approved Plan from Forecast.

Explains variance (auction shifts, promos, inventory, policy changes) and suggests compliant adjustments.

Incrementality‑Adjusted KPIs

Daily KPIs (conversions, revenue, ROAS/CAC) calibrated to causal truth; raw platform reads displayed side‑by‑side for context.

Targets align to your plan’s objective and profit/payback thresholds.

Alerts & Change Log

Real‑time alerts for breached guardrails, out‑of‑band variance (p10/p90), and data drift (taxonomy, window mismatches).

A governed change log: who changed what, when, why, and based on which evidence.

Exports & Integrations

Pacing sheets, guardrail packs, and recommendation CSVs.

Push/pull with buying stacks (where supported) or agency workflows.

How Optimize works (high level)

Uses marginal returns curves and saturation from Measure, lift anchors from geo tests, and incrementality‑adjusted daily KPIs to evaluate where the next dollar performs best.

Applies your policy constraints (caps/floors, ramp‑rates, frequency, concentration) to produce executable recommendations.

Watches real performance against Forecast bands (p50/p10/p90) and raises alerts or suggests re‑plans when downside risk increases.

Deep dives: Causal MMM · Geo‑based Incrementality Testing · Incrementality‑calibrated Attribution · Forecast (Ensemble)

Typical workflows
Daily / Weekly optimization

Open Recommendation Center; review Scale / Cap / Shift items.

Check pacing vs plan and any guardrail alerts.

Accept high‑confidence moves; edit or defer items with operational constraints; document rationale.

Update change log (auto‑captured) and notify channel owners.

Guardrail hygiene (weekly)

Confirm retargeting and brand search are within caps; prospecting floors are met.

Review frequency bands on upper‑funnel (CTV/YouTube/Social) and adjust to increase incremental reach.

Validate ramp‑rates and channel concentration are respected.

Variance management (as needed)

When actuals breach p10 two periods in a row, follow the re‑plan rule: investigate drivers, accept targeted shifts, or escalate to Forecast for a scenario update.

Post‑test calibration

After a decisive geo test, refresh calibration and re‑weight recommendations for affected tactics (e.g., reduce retargeting caps; scale CTV with headroom).

Interpreting Optimize outputs

Impact & confidence: Each recommendation shows estimated incremental revenue/profit lift and a confidence band. Prioritize high impact and high confidence.

Why this action: Traceable rationale—curve position (steep vs flat), test‑anchored lift, and current guardrail status.

Feasibility flags: Notes when an item hits ceilings, frequency limits, or creative capacity constraints.

Decision recipes (ready to use)

Scale steep curves: Increase spend in channels/tactics with high mROAS and headroom until you hit saturation or policy ceilings.

Cap harvesters: Enforce retargeting and brand search caps; tighten recency and negatives; redirect to incremental prospecting.

Protect reach: Maintain prospecting floors in proven upper/mid‑funnel (YouTube/CTV/Social); keep frequency balanced (favor F1–2).

New channel ramp: Follow a step‑up path (e.g., +15–25% WoW) with monitoring; only relax caps after confirmed performance within bands.

Seasonality/promo: During peaks, expect platform ROAS spikes—do not lift caps blindly; prioritize incremental KPIs and profit.

Data requirements & mapping

Minimum viable

Daily or weekly outcomes (orders/revenue/subscriptions) and spend by channel/tactic.

Incrementality‑adjusted KPIs available (or a calibration plan in progress).

Current Approved Plan (pacing), guardrail policy, and taxonomy (Brand vs Non‑Brand; Prospecting vs Retargeting).

Better

Geo splits; creative/audience tags; frequency distribution; promo calendar.

Retail/POS roll‑ups if omnichannel.

Best

Fresh MMM curves and recent geo‑test anchors; inventory/distribution constraints; macro/competitive signals.

Mapping guidelines

One currency, one timezone, aligned ISO weeks.

Enforce naming standards; dedupe overlaps; keep total‑to‑truth (adjusted totals ≤ actuals).

Governance, refresh & versioning

Cadence: Daily/weekly ops; monthly calibration sweep; quarterly MMM refresh and plan approval.

Approvals: Channel owners can accept within policy; larger shifts or policy edits require CMO/CFO sign‑off per your Charter.

Versioning: Guardrail and recommendation changes are logged with evidence links and owners.

Re‑plan triggers: Two consecutive breaches of p10, major supply/policy shock, creative overhaul, or decisive new test results.

Permissions & roles (suggested)

Performance & Media: Execute recommendations; request policy edits; maintain creative/frequency health.

Analytics & Insights: Own calibration, curve updates, variance analysis, and recommendation quality.

CMO/VP Growth: Approve policy changes; arbitrate trade‑offs.

CFO & FP&A: Review profit/payback impacts and concentration risk; sign off on material re‑plans.

Exports & hand‑offs

Guardrail pack: Caps/floors, ramp limits, frequency rules, concentration caps.

Recommendation CSV: Action queue with expected impact, confidence, and due owners.

Pacing worksheet: Channel × week spend with notes on ceilings hit and variance drivers.

Executive note: Weekly summary of actions taken, incremental impact, and risks.

Troubleshooting

Recs fight platform ROAS: Check calibration status—raw vs adjusted KPIs should be side‑by‑side; if not calibrated, fix measurement first.

Nothing to scale: Curves may be flat or constraints too tight—open prospecting floors, refresh creative, or design tests to unlock headroom.

Frequent whiplash: Add stricter ramp‑rate limits and commit to weekly, not daily, budget swings for learning stability.

Hitting ceilings often: Revisit Forecast; maybe the approved plan underestimates attainable reach or ignores capacity.

Omnichannel surprises: Include POS and distribution constraints; cap brand capture in retail media to avoid cannibalization.

FAQs

Do we have to accept every recommendation?
No. Recommendations are decision‑grade suggestions within your policy. Accept high‑impact items, defer low‑confidence ones, and document reasons.

How does Optimize relate to platform bid strategies?
Treat platforms as execution layers. Optimize sets budgets, caps/floors, and constraints so algorithms learn inside incremental guardrails.

Can Optimize automate changes?
Where integrations allow, yes—subject to your permissions and change‑control rules. Otherwise export and apply via your buying stack.

What KPIs should teams target?
Use incrementality‑adjusted ROAS/CAC and payback; raw metrics are for diagnostics only.

How often should guardrails change?
Rarely. Update after decisive tests, MMM refreshes, or strategic shifts—not because of one noisy week.

What “good” looks like

Incrementality‑adjusted KPIs drive daily decisions; raw numbers are context.

Guardrails prevent over‑credit (retargeting/brand search) and protect reach (prospecting floors).

Budget shifts align with steep mROAS; variance stays within Forecast bands.

Actions and outcomes are auditable; debates focus on strategy, not “whose numbers are right?”

Related content

Product Guides: Measure · Forecast · Analyze

Quickstarts: Calibrate attribution · Build a forecast & plan

Methodologies: Incrementality‑calibrated Attribution · Causal MMM · Geo‑based Incrementality Testing

Outcome Playbooks: Maximize Media Efficiency · Acquire New Customers Efficiently · Seasonality & Promotions · Align Marketing & Finance
