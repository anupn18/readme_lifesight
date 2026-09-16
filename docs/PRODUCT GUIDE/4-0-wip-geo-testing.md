---
title: '[4.0][WIP] Geo Experiment'
excerpt: Lifesight 4.0 WIP guide for Geo Experiment.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Geo Experiment

Geo Testing measures incremental impact by comparing selected test markets with a synthetic control built from comparable markets.

In Lifesight 4.0, Geo Testing is the available experiment design. Time Testing and external experiment import are visible as coming soon.

[IMAGE PLACEHOLDER: Experiment design selection with Geo Testing available]

## How Geo Testing works

1. Define the business hypothesis and treatment.
2. Upload historical geo-level KPI data.
3. Configure test cells, duration, markets, and statistical settings.
4. Let Lifesight identify recommended test and control market combinations.
5. Select markets and campaigns, then schedule the test.
6. Monitor progress and calculate lift.
7. Review incremental lift, iROAS, confidence, and market results.

## Treatment options

- **Hold-out** pauses or excludes selected activity in test markets.
- **Scale-up** increases activity in test markets and compares the change with control behavior.

The available treatment can depend on the selected hypothesis.

[VIDEO PLACEHOLDER: Geo Experiment lifecycle from creation to results]

## Key outputs

Geo Experiments can provide measured lift, confidence intervals, p-value, power, iROAS, treatment-versus-control trends, market breakdowns, and recommendations.

Use promoted results to support causal Attribution and eligible MMM calibration workflows.
