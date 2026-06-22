---
title: Advanced Modeling Scenarios
excerpt: How Lifesight models 2nd order effects
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Advanced Modeling Scenarios

Beyond a single national marketing-mix model, Lifesight supports a set of advanced modeling scenarios for when the business question needs more structure - more granularity, multiple geographies or products, relationships between channels, effects that move over time, or a cleaner separation of marketing from baseline demand.

These are :&#x20;

- Granular Models - incrementality at campaign or sub-campaign level
- Hierarchical Models - models across geographies or products, rolled up to a master
- Mediation Effects - crediting channels whose effect flows through other channels
- Interaction Effects - capturing channels that are not independent of one another
- Time-Varying Coefficients - letting an effect evolve as the business changes
- Baseline Modeling - separating marketing's contribution from organic demand

***

### Granular Models

Granular models exist to generate granular MMM insights at the campaign or sub-campaign level - for example, incrementality at a specific TV channel or show, or at the level of an individual KOL or influencer.

- Granular models are run separately from the main model.
- The decomposed KPI data from the main model is passed into another model, along with the sub-components or factors of the independent variable, to model for the granular insight.
- Their purpose is to produce granular insight only - they are used when the iFactor approach to attribution calibration is not possible.
- Granular models are not rolled up into the master model. Additive roll-up is not supported for them.

Lifesight's causal attribution automates granular modeling to campaign and ad set leve. This is covered in more details [here](https://docs.lifesight.io/docs/causal-attribution)

<br />

Hierarchical Models

A brand may want to run models across multiple geographies or product levels.

Lifesight supports hierarchical modeling across one dimension.
The approach is to run separate models across that dimension and then aggregate them into a single master model.
Users can work with the models in two ways:

use an individual model for planning and optimization of a specific geo or product, or
use the national or brand-level master model for overall optimization.

<br />

<br />

Mediation Effects

Some channels do not act on sales directly - they act through another channel. Upper-funnel prospecting lifts branded search, which then converts; television drives site visits that fill the retargeting pools that later convert. The upstream channel is the prime mover, but the downstream channel is where the conversion is recorded.

If a model naively controls for that downstream "mediator", it hands the upstream channel's credit to the channel it was feeding, and concludes that upper-funnel activity does little. Lifesight models these mediation paths explicitly - building on the causal structure of the business - so that upper-funnel channels receive the indirect, downstream credit they actually earn.

Mediation analysis is also how Lifesight captures longer-term effects. As noted on the Adstock page, adstock-ed modeling captures the short-term impact of advertising; the longer-term impact, where brand-building activity feeds future demand and the baseline, is captured through mediation analysis.

Interaction Effects

A standard regression assumes its input variables are independent - that each channel contributes its own slice of the outcome without disturbing the others. In a real marketing system that assumption is often violated, and Lifesight uses nested models to capture the resulting interaction effects.

Today, nested models are built on one key assumption: bottom-of-funnel (BOF) investment is not truly independent of top-of-funnel (TOF) investment. The independence assumption that ordinary regression relies on is violated in this context, so the model captures the TOF-influences-BOF interaction rather than ignoring it.
If you want to capture other interactions beyond TOF influencing BOF, you can let our marketing scientists know and we will incorporate it into the model.
Coming soon: we will make these interaction assumptions transparent in the UI, so users can review and update these "relationships" while the model is being built.

<br />

📘 Mediation and interaction are related but distinct. Mediation is about a channel's effect travelling through another channel (and being credited correctly); interaction is about two channels not being independent, so the presence of one changes the effect of the other.

<br />

Time-Varying Coefficients

A single coefficient is an average over the whole estimation window, but a channel's true effectiveness is a moving curve - it rises as a creative catches on, decays as audiences tire, spikes with seasonality, and bends as the channel saturates.

Time-varying coefficients let an effect evolve over time rather than being frozen as one fixed number, so the model can track effectiveness as it shifts across data regimes instead of smoothing everything into a single average. The adjustments are applied with discipline: enough flexibility to follow genuine change, but not so much that the model starts chasing the noise of thin, recent data.

This is closely tied to adaptive refresh, which operationalizes time-varying behavior at a weekly cadence by adding time-varying adjustments to the coefficients as new data arrives.

Baseline Modeling

Not all of next quarter's revenue comes from the marketing you are measuring. The baseline is the demand that would arrive even if you went dark: the intercept, the trend, seasonality, and the slow-moving stream of organic, returning-customer, word-of-mouth, and brand-equity demand.

For most established businesses, the baseline is large - it typically accounts for anywhere between 30% and 70% of the outcome.
Because it is the bigger number, getting the baseline trajectory right matters as much as getting any single channel's coefficient right. A model that nails a channel's effect but mis-models the baseline will miss the total.
Lifesight models the baseline explicitly (trend, seasonality, and brand equity) and projects it with a baseline-aware ensemble forecasting engine, disciplined by the causal model so the forecast never implies returns the saturation curves rule out.

Baseline modeling also connects back to mediation: a meaningful part of the baseline is the long shadow of past upper-funnel and brand investment, which is why brand-building effort shows up over time as stronger organic demand rather than as an immediate, directly attributed conversion.
