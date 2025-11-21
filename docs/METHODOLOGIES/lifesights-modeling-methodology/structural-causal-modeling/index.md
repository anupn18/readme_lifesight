---
title: Causal Graph in Modeling
excerpt: Causal Directed Acyclical Graph (DAG) based Discovery & Estimation
deprecated: false
hidden: false
metadata:
  robots: index
---
**How to Think About Causal Inference**

Before explaining how Lifesight incorporates Causal AI into its modeling approach, it is important to understand how causality is typically established in data science and econometrics. Broadly, there are two approaches to causal inference:

* Experiment-based causal inference
* Observation-based causal inference

***

1. **Experiment-Based Causal Inference**

In experiment-based causal inference, causality is established through Randomized Controlled Trials (RCTs). This involves creating two statistically similar groups (a treatment group and a control group) and exposing only one of them to a specific intervention — for example, a new advertising campaign, a promotion, or a pricing change.

After a defined period, the outcomes of the treatment group are compared to those of the control group. Because randomization ensures that all other factors are (on average) equal between the two groups, any systematic difference in outcomes can be attributed to the treatment itself.

This makes RCTs the gold standard for causality.

Lifesight fully supports and encourages the use of experiments such as:

* Geo-based lift tests
* Conversion lift studies
* A/B experiments
* Media holdout tests

These experiments are highly valuable inputs for:

* Calibrating MMM
* Validating outcomes
* Informing priors
* Improving confidence in causal impact

However, experiments come with practical limitations:

* They are expensive and time-consuming
* They cannot be run on all channels or regions simultaneously
* They often cover short time horizons
* They do not scale continuously with business complexity
* This is where the second approach becomes essential.

***

2. **Observation-Based Causal Inference**

Observation-based causal inference attempts to infer cause-and-effect relationships from historical, non-randomized data - the type of data most organizations already have in abundance.

This field is also known as **Causal Inference from Observational Data** and is closely associated with the concept of** Natural Experiments**, where naturally occurring variations in the real world act as proxies for controlled tests.

**When Lifesight refers to “Causal MMM”, it primarily means incorporating robust techniques from observation-based causal inference into the Marketing Mix Modeling process. ** This allows Lifesight to extract causal insights even when true randomized experiments are unavailable.

Within this domain, there are two major schools of thought:

* The Pearlian framework (Judea Pearl)
* The Rubin framework (Donald Rubin)
