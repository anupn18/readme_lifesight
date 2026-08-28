---
title: '[4.0][WIP] Build a schema for Geo Experiments'
excerpt: >-
  Define the KPI and geographic dimension a geo test needs, so incremental lift
  can be measured against matched control regions.
hidden: false
---

# Build a schema for Geo Experiments

A geo experiment measures incrementality by doing something different in one set of regions and not in another, then comparing what happened. It is the closest thing to a controlled experiment that most marketing can run, and it produces evidence rather than an estimate.

This schema defines what a geo test reads: the outcome being measured, the geographic dimension that splits test from control, and the media being tested.

## When to use it

Choose this schema type when you want to:

- measure the true incremental lift of a channel by holding it out somewhere
- prove whether a channel is worth its budget, rather than inferring it
- produce a result you can use to calibrate a mix model

If you want to decompose contribution across all channels over time instead, use [Build a schema for Marketing Mix Modelling](https://docs.lifesight.io/docs/4-0-wip-schema-mmm).

## What it needs

The wizard states the requirements on the first step: **test and control regions**, a **geo dimension**, and **revenue lift**.

That third requirement is worth dwelling on. A geo test compares regions, so your KPI has to be reportable per region. If your revenue data has no geography attached, a geo test cannot be run on it no matter how the schema is configured.

This is usually where the earlier tabs matter:

- The geographic dimension must be mapped in [Data Transformation](https://docs.lifesight.io/docs/4-0-wip-data-transformation) and flagged as a measurement dimension
- Sources that cover one market but do not report geography per row need a country or region set with [Set a fixed value for a source](https://docs.lifesight.io/docs/4-0-wip-fixed-value-source)
- Media being tested needs to be classified in [Data Taxonomy](https://docs.lifesight.io/docs/4-0-wip-data-taxonomy) so the test can target a specific tactic

## Step 1: Model Schema Type

Name the schema after the test it supports, then select **Geo Experiments**.

You can select both schema types if one variable set should power a mix model and geo testing. A schema is method agnostic, so a well defined set of variables can serve both.

![Choosing the schema type](https://files.readme.io/4baa47fe72d55cfb3df87a9e139b68b5d9501b9f75147e8c910db97caa331f57-model-schema-type.png)

## Step 2: Variables

**Primary KPI.** The outcome the test measures, most often revenue or orders. It must be available per region at the granularity of your test.

**Dimensional / hierarchical model.** For geo work this is where the geographic dimension does its job, letting the schema read the outcome per region rather than as one national number.

**Paid Media.** The channels and tactics the test will manipulate. If you are holding out paid social in a set of regions, that tactic needs to be here.

**Organic and Contextual.** Still worth including. Regional differences in seasonality, promotions or store openings are exactly the kind of thing that can be mistaken for a treatment effect if unaccounted for.

![Choosing variables for the schema](https://files.readme.io/33f2c89ed584e193201ddafef6667d47ef4101256d3f74172b1757e86048936e-model-schema-variables.png)

## Steps 3 and 4

**Causal Graph** captures the relationships you are confident about, and **Preview** is the final check before saving.

For a geo schema the checklist is narrower: is the KPI reportable per region, is the geographic dimension present on every contributing source, and is the media you intend to test represented as its own tactic.

## Where this shows up in the rest of Lifesight

**Experiments** reads this schema when you design a geo test. Market selection and power analysis both depend on having a KPI available per region, which is precisely what the schema guarantees.

**Geo Experiment Design** uses it to identify comparable test and control markets. Poor regional data produces poorly matched markets, and poorly matched markets produce a result you cannot trust.

**Geo Experiment Insights** reports the measured lift against the same definitions, so the number the test produces is directly comparable to what your other reporting says.

**Model Calibration** is where the two halves meet. A geo test produces a high confidence estimate of incrementality for one channel, and that result can be fed back to calibrate your mix model. For that to work, both have to be speaking about the same KPI and the same tactic, which is why using one consistent schema definition across both matters.

**Automated deployment of experiments** can push the resulting campaign changes to Meta or Google, which relies on the tested media being correctly classified.

## Common questions

**My revenue has no region. Can I still run a geo test?**
Not meaningfully. The comparison is between regions, so the outcome has to be attributable to one. Getting regional data into Lifesight is the prerequisite.

**Can one schema serve both a mix model and a geo test?**
Yes. Select both types on the first step. The variables largely overlap, and keeping them in one definition is what makes calibration straightforward later.

**How granular should the geography be?**
Granular enough to give you enough matched markets to compare, coarse enough that each has a stable outcome signal. Very fine geography produces noisy regions that are hard to match.

**Do I need contextual variables for a geo test?**
They help. A regional promotion or a store opening during the test window can look exactly like a treatment effect if the model has no way to know about it.
