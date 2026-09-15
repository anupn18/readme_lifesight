---
title: Ensemble Forecasting
excerpt: How it works and how Lifesight implements it end‑to‑end.
deprecated: false
hidden: true
metadata:
  robots: index
---
Ensemble forecasting combines multiple models—causal MMM, time‑series with exogenous drivers, and experiment‑informed uplift—into a single, probabilistic forecast that powers profit‑aligned planning and risk‑aware decision‑making.

At a glance

Answers: “What outcomes should we expect under each plan?” “How wide is the upside/downside?” “Which assumptions drive risk?”

Best for: 4–12 week planning cycles, quarterly re‑plans, seasonal peaks, and scenario testing (efficiency vs. growth).

Inputs: Causal MMM outputs and marginal curves, geo‑test lift, attribution‑calibrated daily signals, price/promo calendar, seasonality/holidays, retail/POS (if relevant), macro/competitive proxies.

Outputs: Probabilistic forecasts (p50/p10/p90), channel/week spend plans that respect constraints, and sensitivity insights for the CFO and channel leads.

Privacy‑first: Works on aggregated data; no user‑level identifiers.

Read next: Causal MMM · Geo‑based Incrementality Testing · Product Guide: Forecast — Forecast to achieve profit and growth

What ensemble forecasting is (and why it beats single‑model plans)

No single model is best across all horizons, data regimes, and market shocks. Ensemble forecasting blends complementary methods so each contributes what it does best:

Causal MMM provides structural understanding (baseline vs. media, diminishing returns, saturation) and marginal curves to simulate “next‑dollar” effects.

Time‑series models with exogenous drivers capture recurring patterns (trend/seasonality, holidays), short‑term dynamics, and base demand shifts.

Experiment‑informed uplift brings causal truth from geo‑tests into the future, anchoring channels where observational data is ambiguous.

Adjusted attribution signals provide near‑term, granular pulse to reflect weekly activation changes without over‑relying on correlation.

The result is a stacked, weighted forecast that’s more accurate on average and, crucially, honest about uncertainty.

The Lifesight ensemble (components & roles)

Causal MMM forward projection

Uses the latest MMM to project outcomes under candidate spend paths.

Respects adstock/lag and saturation to model carryover and diminishing returns.

Provides mROAS curves and channel response functions that drive scenario realism.

Base‑demand time‑series

Dedicated models for baseline (non‑media) demand using trend, seasonality, holidays, and structural break detection.

Incorporates exogenous regressors: price/promos, distribution/retail, macro proxies (e.g., category interest, weather), and brand/search signals.

Experiment‑anchored uplift

Applies lift factors from recent geo tests to relevant channels/tactics, with decay logic and refresh cadence.

Prioritizes test evidence where confidence is high; falls back to MMM where tests don’t exist.

Attribution‑calibrated micro‑signals

Uses incrementality‑adjusted weekly/daily KPIs to reflect short‑term shifts (creative, audience, auction dynamics).

Prevents overreaction to raw platform noise by enforcing ensemble guardrails.

Fusion & weighting layer

Blends component forecasts using performance‑by‑horizon weighting and stability checks.

Detects regime changes (e.g., new promo policies, supply constraints) and re‑weights toward components that historically perform better in similar conditions.

Produces quantile forecasts (p50/p10/p90) rather than false‑precision point estimates.

How the ensemble powers planning

Scenario inputs: Budget envelope, objective (profit, revenue, CAC/payback), constraints (floors/ceilings, ramp rates, geo/retail windows), and business rules.

Simulation engine: Feeds each candidate plan through MMM curves (for media‑driven lift) plus base‑demand models and experiment uplifts.

Uncertainty propagation: Varies key inputs (media response, promo intensity, conversion rates) to generate bands around outcomes.

Decision outputs: Expected revenue/profit/CAC per scenario, risk bands, and sensitivity drivers (which assumptions move results most).

What you choose: Typically compare Efficiency‑first, Balanced, and Growth‑first scenarios, then approve the plan with the best objective score and acceptable downside risk.

Data requirements (good → better → best)

Good: Weekly outcomes (orders/revenue/subscriptions), channel spend, holiday/seasonality calendar.

Better: Price & promo calendar, geo splits, retail/POS roll‑ups, share‑of‑search/brand indicators, incrementality‑adjusted daily KPIs.

Best: Recent geo‑test results for major channels, creative/placement tags, inventory/distribution flags, macro or competitive proxies.

Tip: Consistent taxonomy (Brand vs. Non‑Brand; Prospecting vs. Retargeting) matters more than extreme granularity.

Uncertainty and risk management (what the bands mean)

p50 (median): The most likely outcome given current evidence and assumptions.

p10 / p90: Downside and upside bounds capturing plausible variance in response, conversion, and demand.

Use in practice:

CFO cares about downside exposure (p10) and whether the plan meets profit/payback constraints in a tough week.

Channel leads use bands to set guardrails and pre‑agree on what triggers re‑plans.

Evaluation & governance

Rolling backtests: Compare ensemble predictions vs. realized outcomes across past windows; monitor WAPE/MAPE and interval coverage (how often actuals fall within bands).

Decision utility checks: Did the chosen plan outperform the alternatives on realized outcomes?

Versioning: Each forecast run is versioned with inputs, assumptions, weights, and release notes.

Drift monitoring: Alerts when actuals repeatedly beat/miss bands—triggering retraining, re‑weighting, or new tests.

Sign‑offs: Marketing, Analytics, and Finance sign the approved plan with a one‑line rationale.

How Lifesight integrates ensemble forecasting into your workflow

Measure → Curves: Refresh MMM and marginal returns.

Test → Anchors: Run geo tests on debated channels; apply lift to calibrate.

Calibrate → Daily truth: Use incrementality‑adjusted attribution for near‑term pulse.

Forecast → Scenarios: Generate 2–3 plan options with uncertainty bands.

Optimize → Guardrails: Translate the selected plan into caps/floors and pacing.

Analyze → Track: Monitor realized vs. forecast, variance drivers, and re‑plan triggers.

Practical guidance

Keep objectives consistent across scenarios (don’t compare profit vs. revenue apples‑to‑oranges).

Stress‑test assumptions: What happens if CPMs inflate, promo response softens, or a supply constraint hits?

Respect execution realities: Add ramp‑rate limits, creative refresh lead times, and channel minimums so plans are feasible.

Don’t chase the last decimal: Prefer well‑calibrated bands to brittle point optimism.

Close the loop: Feed variance analysis back into MMM features and the testing roadmap.

Common pitfalls (and how to avoid them)

Single‑model overconfidence → Blend methods; publish bands; monitor interval coverage.

Ignoring saturation → Plans that “optimize” to average ROAS will over‑spend flat regions; rely on marginal curves.

Unrealistic ramps → Add week‑over‑week spend change caps and creative capacity checks.

Promo blindness → Include promo calendars and price effects in base‑demand models.

Out‑of‑date calibration → Refresh lift factors after each decisive geo test; retire stale ones.

Data leakage → Keep future information out of training windows; lock feature availability to real‑time constraints.

FAQs

How often do you refresh the ensemble?
At least monthly and after major evidence changes (new MMM run, decisive geo test, significant promo/supply shift).

Can it handle new channels with little history?
Yes—use experiment‑anchored uplift, analog priors from similar channels, and conservative weights until more data accrues.

What’s the difference between a forecast and a target?
The forecast is what you expect given evidence; a target is what you want to achieve. We plan to targets but manage to forecasts with risk awareness.

Does this replace Finance’s forecast?
It complements it. We provide a marketing‑sourced, causally calibrated view that Finance can reconcile to P&L with agreed assumptions and bands.

How are uncertainty bands determined?
By propagating uncertainty from model parameters, input assumptions (e.g., spend, conversion), and exogenous volatility using simulation and quantile estimation—summarized as p10/p50/p90.

Read next

Product Guide: Forecast — Forecast to achieve profit and growth

Quickstart: Build a forecast & plan

Causal MMM

Geo‑based Incrementality Testing

Outcome Playbook: Forecast profitable growth
