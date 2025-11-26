---
title: Causal Reasoning in Modeling
excerpt: A comprehensive introduction to Causal Inference in Modeling
deprecated: false
hidden: false
metadata:
  robots: index
---
## How to Think About Causal Inference

Before explaining how Lifesight incorporates Causal reasoning into its modeling approach, it is important to understand how causality is typically established in data science and econometrics.

Broadly, there are two approaches to causal inference:

* Experiment-based causal inference
* Observation-based causal inference

***

### 1. Experiment-Based Causal Inference

In experiment-based causal inference, causality is established through Randomized Controlled Trials (RCTs). This involves creating two statistically similar groups (a treatment group and a control group) and exposing only one of them to a specific intervention — for example, a new advertising campaign, a promotion, or a pricing change.

After a defined period, the outcomes of the treatment group are compared to those of the control group. Because randomization ensures that all other factors are (on average) equal between the two groups, any systematic difference in outcomes can be attributed to the treatment itself.

This makes RCTs the gold standard for causality.

Lifesight fully supports and encourages the use of experiments such as Geo-based lift tests & Media holdout tests

These experiments are highly valuable inputs for:

* Calibrating MMM
* Validating outcomes
* Informing priors
* Improving confidence in causal impact

***

### 2. Observation-Based Causal Inference

Observation-based causal inference attempts to infer cause-and-effect relationships from historical, non-randomized data - the type of data most organizations already have in abundance.

This field is also known as **Causal Inference from Observational Data** and is closely associated with the concept of **Natural Experiments**, where naturally occurring variations in the real world act as proxies for controlled tests.

**When Lifesight refers to “Causal MMM”, it primarily means incorporating robust techniques from observation-based causal inference into the Marketing Mix Modeling process.** This allows Lifesight to extract causal insights even when true randomized experiments are unavailable.

Within this domain, there are two major schools of thought:

* The Pearlian framework (Judea Pearl)
* The Rubin framework (Donald Rubin)

***

### The Pearlian Approach

The Pearlian school of causality is built around the concept of **Structural Causal Models (SCMs)** and **Causal Directed Acyclic Graphs (DAGs)** .

In this framework:

* Causal relationships are explicitly encoded as a graph
* Assumptions are transparently stated
* Cause-and-effect paths can be visualized
* Direct and indirect effects can be computed mathematically

This approach answers questions such as:

* What caused what?
* How does influence propagate through the system?
* What happens if I intervene on this variable?

This aligns perfectly with the needs of Marketing Mix Modeling, where channels interact, sequence matters, and mediation plays a critical role (e.g., upper funnel → lower funnel → conversions).

### The Rubin Approach

The Rubin framework, also known as the Potential Outcomes framework, focuses on estimating causal effects by comparing observed outcomes with counterfactual outcomes - i.e., what would have happened if an intervention had not taken place.

This approach underpins many statistical techniques such as:

* Difference-in-Differences (DiD)
* Propensity Score Matching
* Synthetic controls
* Regression Discontinuity

It is highly effective for evaluating the average treatment effect of specific interventions but is less suited to modeling complex multi-variable systems with feedback loops, interactions, and mediation chains.

***

## Lifesight’s Position

Lifesight’s MMM framework is primarily grounded in the Pearlian paradigm, using Directed Acyclic Graphs (DAGs) as the structural backbone of the model.

This is because DAGs allow us to explicitly represent:

* Funnel progression (awareness → consideration → conversion)
* Interdependencies between channels
* Mediated and halo effects
* Feedback loops and latent drivers

In other words, the DAG acts as a structural blueprint of the business and its marketing system — a representation that exists independently of the actual data values : **A Digital Clone**. At the same time, Lifesight does not treat these two schools as mutually exclusive.

In keeping with our principle of Algorithmic Fit, Lifesight:

* Uses Pearlian DAGs for structure, interpretability, and mediation modeling
* Leverages Rubin-style experimental results to calibrate and validate causal strength
* Incorporates both into a unified, transparent, and robust framework

This hybrid philosophy enables Lifesight to offer the best of both worlds:

* The structural clarity of causal graphs
* The practical evidence of counterfactual testing
* The scalability of machine learning
* The credibility of experimentation

***

## Why This Matters for MMM

Traditional MMM frameworks treat channels mainly as independent variables in a regression equation. Even when interactions are included, the assumed structure is implicit and opaque.

By contrast, Lifesight’s causal DAG approach:

* Makes assumptions visible and editable
* Separates structure from estimation
* Captures real marketing dynamics
* Enables true mediation analysis
* Improves interpretability for stakeholders
* Aligns models with how businesses actually operate

Next we will disc use the specifics around Causal Discovery & Estimation. We will also discuss how this estimation back-propagates along the causal dag in reverse topological order

Learn more about Causal Discovery [here](https://docs.lifesight.io/update/docs/causal-discovery-estimation#/)

<br />
