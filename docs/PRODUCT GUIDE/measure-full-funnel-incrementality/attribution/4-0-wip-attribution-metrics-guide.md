---
title: '[4.0][WIP] Attribution metrics guide'
excerpt: Lifesight 4.0 WIP guide for Attribution metrics guide.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Attribution Metrics Guide

Attribution in Lifesight 4.0 combines spend, platform-reported performance, incremental performance, and plan pacing metrics.

[IMAGE PLACEHOLDER: Attribution Breakdown with metric columns]

## Incremental performance

| Metric | Definition | Formula |
| --- | --- | --- |
| Incremental Revenue | Revenue estimated to be causally driven by advertising | Provided by Lifesight measurement |
| iROAS | Incremental return for each unit of spend | Incremental Revenue / Actual Spend |
| Incremental Conversions | Conversions estimated to be causally driven by advertising | Platform Conversions adjusted by incrementality evidence |
| iCPA | Cost per incremental conversion | Actual Spend / Incremental Conversions |
| Incrementality Factor | Share of platform-reported revenue estimated to be incremental | Incremental Revenue / Platform Revenue |
| Marginal ROAS | Incremental revenue expected from the next unit of spend | Derived from the promoted model |

## Platform-reported performance

| Metric | Definition | Formula |
| --- | --- | --- |
| Platform Revenue | Revenue reported by the advertising platform | Platform value |
| Platform ROAS | Platform-reported return on spend | Platform Revenue / Actual Spend |
| Platform Conversions | Conversions reported by the advertising platform | Platform value |
| Platform CPA | Platform-reported cost per conversion | Actual Spend / Platform Conversions |
| Impressions | Number of ad impressions served | Platform value |
| Clicks | Number of ad clicks recorded | Platform value |

## Spend and pacing

| Metric | Definition | Formula |
| --- | --- | --- |
| Actual Spend | Spend recorded during the selected period | Platform value |
| Planned Spend | Budget allocated by the active scenario | Scenario value |
| Pacing | Actual spend relative to planned spend to date | Actual Spend / Planned Spend to Date |
| Total Delta | Cumulative difference from plan | Actual Spend minus Planned Spend |
| Daily Average Spend | Average spend per elapsed day | Actual Spend / Days Elapsed |
| Daily Average Planned | Expected daily rate to date | Planned Spend to Date / Days Elapsed |
| Daily Gap | Difference between actual and planned daily rates | Daily Average Spend minus Daily Average Planned |
| Recommended Daily | Catch-up adjusted daily spend for the next seven days | Remaining Budget / Remaining Days |

## Recommendations

- **Scale** indicates under-pacing against the active plan.
- **Maintain** indicates pacing is within the expected range.
- **Reduce** indicates over-pacing against the active plan.

[VIDEO PLACEHOLDER: Using Choose columns to inspect attribution metrics]

Metric availability depends on the connected platforms, promoted measurement assets, and selected reporting range. Columns with no received data or only zero values may be hidden automatically and can be revealed from the table controls.
