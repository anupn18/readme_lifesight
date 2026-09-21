---
title: '[4.0][WIP] Target benchmark'
excerpt: Lifesight 4.0 WIP guide for Target benchmark.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Target Benchmark

The target scenario controls the benchmark, planned spend, and causal recommendations displayed in Attribution.

[IMAGE PLACEHOLDER: Target scenario control in the Attribution header]

## Configure the target scenario

1. Go to **Measure > Attribution**.
2. Select the scenario chip or the causal configuration control in the header.
3. Choose an available metric or scenario.
4. Enter a benchmark value when the selected metric requires one.
5. Review the reference and forecast periods when they are provided.
6. Select **Confirm**.

[VIDEO PLACEHOLDER: Configuring a target scenario]

## How recommendations work

For scenario-based causal recommendations, Lifesight compares spend in the reference period with spend in the forecast period. Recommendations are derived from the promoted MMM scenario output.

The Breakdown displays:

- **Scale** when an entity is under-pacing
- **Maintain** when an entity is pacing near plan
- **Reduce** when an entity is over-pacing

The recommendation can include the absolute daily gap and next-period spend guidance where available.

## Review the active benchmark

After confirmation, the selected benchmark appears in the scenario chip. Review the Overview and Breakdown again because planned spend, pacing, and recommendations can change with the active scenario.

[IMAGE PLACEHOLDER: Updated pacing and recommendations after benchmark selection]

> Use a scenario and analysis period that are relevant to the current decision. Recommendations based on an outdated plan may no longer be actionable.
