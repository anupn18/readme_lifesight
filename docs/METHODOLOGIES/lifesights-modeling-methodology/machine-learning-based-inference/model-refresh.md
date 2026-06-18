---
title: Model Refresh
excerpt: How Lifesight keeps a marketing mix model current as the business moves.
deprecated: false
hidden: true
metadata:
  robots: index
---
A coefficient is an average, and the effectiveness it summarizes is a moving curve - it rises as a creative catches on, decays as audiences tire, and bends as a channel saturates. A model fit once and quoted for a year slowly stops describing reality, because both the data and the underlying relationships drift over time. Lifesight keeps models current through two distinct mechanisms operating at different cadences: a frequent refresh and a periodic retraining.

> 📘 Refresh vs. retraining. A refresh passes new data through the existing model structure and hyper-parameters, letting the coefficients adapt. A retraining rebuilds the model - re-searching the hyper-parameter space - while inheriting what previous runs learned.

## Weekly model refresh

At Lifesight, model refresh happens at a weekly cadence. A refresh passes new data through the existing hyper-parameters while letting the coefficients adapt to the new data. The structure the model already learned - the adstock decay, the saturation shapes, the causal constraints - is held fixed, so the refresh is fast and stable, and the coefficients move only as much as the new weeks of data justify. This keeps incrementality, ROAS, and marginal-return estimates current without the cost or added variance of a full rebuild every week.

## Time Varying Adaptive refresh

A standard refresh updates the coefficients to fit the latest data but still treats each effect as a single, updated average. Adaptive refresh goes further: it adds time-varying adjustments to the coefficients, so the model can track effectiveness as it evolves across new data regimes rather than smoothing everything back into one number.

This is how the model keeps up with shifting business realities - a channel that has recently fatigued, a creative that has just caught on, a season that is behaving differently this year - instead of waiting for the next retraining to notice. The adjustments are applied with discipline: enough flexibility to follow genuine change, but not so much that the model starts chasing the noise of thin, recent data.

### Partial refresh

Real data rarely arrives all at once - a platform's numbers may lag, a feed may break, or an offline source may close late. Lifesight supports partial refresh: the model is refreshed even when some input variables are missing.

In that case, the platform reports what is measured and marks the rest as unknown, to be updated once all the data is available. This means a marketer always has a current, honest read - with the gaps clearly flagged - rather than a stale model or a falsely complete one.

### Model retraining

Refreshing keeps an existing model current; retraining rebuilds it. Model retraining is typically done quarterly, or on a need basis - for example after a structural break such as a major pricing change, a new market, or a product launch, or when drift monitoring shows the current structure no longer fits.

A retraining re-runs the full modeling pipeline, including the evolutionary search across candidate adstock, saturation, and model shapes - but it does not start blind. It inherits strong priors from previous runs and adds meaningful constraints to the hyper-parameter search, so each generation of the model stands on the evidence accumulated by the ones before it rather than rediscovering the business from scratch. Results from incrementality experiments feed the same priors through calibration.

### At a glance

| Mechanism        | Cadence                             | What it does                                                                                        |
| ---------------- | ----------------------------------- | --------------------------------------------------------------------------------------------------- |
| Weekly Refresh   | Weekly                              | Passes new data through existing hyper-parameters; coefficients adapt while structure is held fixed |
| Adaptive Refresh | Weekly (within refresh)             | Adds time-varying adjustments so coefficients track evolving regimes, not just a single average     |
| Partial Refresh  | As needed (based on missing inputs) | Refreshes on available data; missing inputs reported as unknown until complete                      |
| Retraining       | Quarterly / On need                 | Full rebuild and hyper-parameter re-search, inheriting strong priors and added constraints          |

<br />

Together, this cadence is what keeps a model from becoming a confident relic. Trust in a model is not a one-time grant; it is renewed every cycle - weekly as the coefficients adapt, and quarterly as the structure is rebuilt on everything learned so far.
