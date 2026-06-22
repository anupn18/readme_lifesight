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
### Advanced Modeling Scenarios

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

***

### Hierarchical Models

A brand may want to run models across multiple geographies, product levels, customer segments, sales channels and more. Lifesight supports hierarchical modeling across multiple dimensions.

To have an approach that's generalisable across multiple types of dimensions, we have a practice of running models at separate levels , i.e, we run separate models across these dimensions and then aggregate them into a single master model.

<br />Users can work with the models in two ways:

1. use an individual model for planning and optimization of a specific geo or product, or
2. use the national or brand-level master model for overall optimization.

This additive approach - running separate models per slice of the dimension and aggregating them into a master - is deliberately different from the partial-pooling (multilevel) approach often associated with hierarchical models, and it carries several practical benefits:

- Generalizable across any dimension. The same approach works whether the dimension is geography, product, sales channel, or any other slice of the business - it is not tied to a particular kind of grouping.
- No limiting assumptions of partial pooling. Partial pooling shrinks every unit's estimate toward a shared mean and assumes the units are exchangeable "siblings from one family". The additive approach makes no such assumption, so it does not flatten the genuine differences between slices or contaminate them by pooling units that are not truly comparable.
- Calibratable with strong priors. Each model can be anchored with strong, objective priors - ideally informed by incrementality experiments - through calibration.
- Common or separate weak priors. The adstock and saturation weak priors can be shared across slices where that makes sense, or set separately where a slice behaves differently.
- Different causal structure per slice. Each slice can carry its own DAG structure, so a geography or product with genuinely different dynamics is modeled on its own causal map rather than forced onto a single shared one.
- Planning at parent or child level. The same setup supports optimization at the aggregated parent level (the master model) and at the individual child level (each slice's own model).

<br />

***

### Mediation Effects

Some channels do not act on sales directly - they act through another channel. Upper-funnel prospecting lifts branded search, which then converts; television drives site visits that fill the retargeting pools that later convert. The upstream channel is the prime mover, but the downstream channel is where the conversion is recorded.

If a model naively controls for that downstream "mediator", it hands the upstream channel's credit to the channel it was feeding, and concludes that upper-funnel activity does little. Lifesight models these mediation paths explicitly - building on the causal structure of the business - so that upper-funnel channels receive the indirect, downstream credit they actually earn.

Mediation analysis is also how Lifesight captures longer-term effects. As noted on the Adstock page, adstock-ed modeling captures the short-term impact of advertising; the longer-term impact, where brand-building activity feeds future demand and the baseline, is captured through mediation analysis.

Details of back-propogation of credits to direct/indirect effects is captured [here](https://docs.lifesight.io/docs/backpropogation-effect-adjustments)&#x20;

### Interaction Effects

A standard regression assumes its input variables are independent - that each channel contributes its own slice of the outcome without disturbing the others. In a real marketing system that assumption is often violated, and Lifesight uses nested models to capture the resulting interaction effects.

Today, nested models are built on one key assumption: bottom-of-funnel (BOF) investment is not truly independent of top-of-funnel (TOF) investment. The independence assumption that ordinary regression relies on is violated in this context, so the model captures the TOF-influences-BOF interaction rather than ignoring it.
If you want to capture other interactions beyond TOF influencing BOF, you can let our marketing scientists know and we will incorporate it into the model.
Coming soon: we will make these interaction assumptions transparent in the UI, so users can review and update these "relationships" while the model is being built.

> 📘 Mediation and interaction are related but distinct. Mediation is about a channel's effect travelling through another channel (and being credited correctly); interaction is about two channels not being independent, so the presence of one changes the effect of the other.

## Understanding Interaction Effects in Marketing Mix Modeling

In the dynamic world of e-commerce, accurately attributing sales and key performance indicators (KPIs) to specific marketing activities is essential for optimizing strategies and maximizing return on investment (ROI). Marketing Mix Modeling (MMM) serves as a crucial analytical tool in this process, enabling businesses to quantify the impact of various marketing channels. However, one sophisticated concept that plays a significant role in MMM is interaction effects. This article explores what interaction effects are, their importance in MMM, real-world examples, and how Lifesight’s Unified Marketing Measurement Platform effectively manages these effects to ensure precise and actionable insights.

### What are Interaction Effects in Marketing Mix Modeling?

Interaction effects occur when the combined influence of two or more marketing channels on sales or other KPIs is different from the sum of their individual effects. In other words, the impact of one marketing channel depends on the presence or intensity of another. These interactions can either amplify (positive interaction) or diminish (negative interaction) the overall effectiveness of marketing efforts.

#### Key Points:

- Synergistic Effects: When two channels work together to produce a greater effect than the sum of their individual contributions.
- Antagonistic Effects: When one channel’s effectiveness reduces the impact of another.
- Context-Dependent: Interaction effects can vary based on factors such as timing, audience, and market conditions.

#### Why Interaction Effects Matter in MMM

Understanding and accounting for interaction effects in MMM is crucial for several reasons:

#### Accurate Attribution:

- Holistic Understanding: Interaction effects provide a more comprehensive view of how marketing channels influence each other and contribute to overall performance.
- Preventing Misattribution: Ignoring interaction effects can lead to incorrect attribution of sales to individual channels, skewing performance metrics.

#### Optimized Marketing Strategies:

- Strategic Synergies: Identifying positive interactions allows businesses to leverage synergistic combinations of channels for enhanced effectiveness.
- Mitigating Negative Interactions: Recognizing and addressing negative interactions helps in refining marketing strategies to prevent channels from undermining each other.

#### Enhanced ROI Calculation:

- Precise Measurement: By accounting for interaction effects, businesses can calculate the true ROI of each marketing channel, leading to more informed budget allocations.
- Resource Efficiency: Optimizing based on accurate interaction assessments ensures that marketing resources are invested where they yield the highest returns.

#### Informed Decision-Making:

- Data-Driven Insights: Interaction effects offer deeper insights into the complexities of marketing dynamics, enabling more nuanced and effective decision-making.
- Future Planning: Understanding interactions aids in forecasting future performance and planning integrated marketing campaigns.

<br />

***

### Time-Varying Coefficients

A single coefficient is an average over the whole estimation window, but a channel's true effectiveness is a moving curve - it rises as a creative catches on, decays as audiences tire, spikes with seasonality, and bends as the channel saturates.

Time-varying coefficients let an effect evolve over time rather than being frozen as one fixed number, so the model can track effectiveness as it shifts across data regimes instead of smoothing everything into a single average. The adjustments are applied with discipline: enough flexibility to follow genuine change, but not so much that the model starts chasing the noise of thin, recent data.

This is closely tied to adaptive refresh, which operationalizes time-varying behavior at a weekly cadence by adding time-varying adjustments to the coefficients as new data arrives.

***

###

Baseline Modeling

Not all of next quarter's revenue comes from the marketing you are measuring. The baseline is the demand that would arrive even if you went dark: the intercept, the trend, seasonality, and the slow-moving stream of organic, returning-customer, word-of-mouth, and brand-equity demand.

For most established businesses, the baseline is large - it typically accounts for anywhere between 30% and 70% of the outcome.
Because it is the bigger number, getting the baseline trajectory right matters as much as getting any single channel's coefficient right. A model that nails a channel's effect but mis-models the baseline will miss the total.
Lifesight models the baseline explicitly (trend, seasonality, and brand equity) and projects it with a baseline-aware ensemble forecasting engine, disciplined by the causal model so the forecast never implies returns the saturation curves rule out.

To quantify the baseline, Lifesight decomposes the revenue or outcome into seasonality and trend. Seasonality captures the repeating part of the business - the patterns that recur week to week or season to season - while trend quantifies the cumulative part, the slow-moving direction the business is heading in. For this decomposition we use Fourier decomposition or Prophet decomposition. These are made part of the modeling itself, and their output is what quantifies the baseline.

Baseline modeling also connects back to mediation: a meaningful part of the baseline is the long shadow of past upper-funnel and brand investment, which is why brand-building effort shows up over time as stronger organic demand rather than as an immediate, directly attributed conversion.

Long-Term Effect Estimation

Long-term effect estimation brings together mediation analysis and baseline modeling to understand how top-of-funnel (TOF) activity supports the slow-moving trend component of the baseline.

This is a default assumption in the DAG: TOF investment is modeled as feeding the trend rather than only the immediate conversion. The indirect effect captured through this path lets Lifesight quantify how much of the change in trend is supported by TOF investments - in other words, how much of the baseline's upward (or downward) drift is actually the long shadow of upper-funnel spend.

Beyond this, Lifesight further decomposes the trend into brand momentum and category momentum. For this we use share of search as a proxy, which makes it possible to understand how the brand and the category are growing both in absolute terms and relative to each other. Separating the two answers a question MMM usually cannot: how much of the trend is a rising tide lifting the whole category, and how much is the brand genuinely gaining ground within it.

***

### Halo Effects

In the realm of Marketing Mix Modeling (MMM), accurately attributing sales and other key performance indicators (KPIs) to specific marketing activities is crucial for optimizing strategies and maximizing return on investment (ROI). However, one common challenge that can distort these attributions is the Halo Effect. This article explores what the halo effect is, its implications in MMM, and how Lifesight’s Unified Marketing Measurement Platform effectively manages and mitigates its impact to ensure precise and actionable insights.

#### What is the Halo Effect?

The Halo Effect is a cognitive bias where the perception of one positive attribute of a marketing channel or campaign influences the overall perception of its effectiveness, potentially skewing the true measurement of its performance. In Marketing Mix Modeling, this bias can lead to the overestimation or underestimation of a marketing channel’s actual contribution to sales and KPIs.

#### Key Points:

Bias in Attribution: The halo effect causes marketers to attribute positive results to all activities of a successful channel, not just the effective ones.<br />Distorted Insights: This bias can distort the insights derived from MMM, leading to misguided strategic decisions and budget allocations.

### Why is the Halo Effect Important in MMM?

Understanding and mitigating the halo effect is essential for several reasons:

#### Accurate Attribution:

- True Performance Measurement: The halo effect can obscure the true performance of individual marketing channels, making it difficult to assess their actual impact.
- Resource Allocation: Misattributed effectiveness can lead to inefficient allocation of marketing budgets, investing more in channels that appear effective due to bias rather than actual performance.

#### Strategic Decision-Making:

- Informed Strategies: Without accounting for the halo effect, strategies based on flawed data can hinder business growth and ROI.
- Competitive Advantage: Accurate insights free from bias provide a competitive edge, enabling more precise and effective marketing strategies.

#### Optimizing Marketing Spend:

- Maximized ROI: Proper attribution ensures that marketing spend is directed towards channels that genuinely drive results, maximizing overall ROI.
- Reduced Waste: Prevents overspending on ineffective channels influenced by the halo effect, reducing marketing waste.

<br />
