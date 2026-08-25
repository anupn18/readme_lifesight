---
title: '[4.0][WIP] Campaigns'
excerpt: Analyze campaign-level marketing performance and contribution.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Campaign-level analysis helps connect modelled channel performance with the activity reported by advertising platforms. In Lifesight 4.0, campaign and creative reporting depends on the taxonomy and integration data configured for the workspace.

## Before You Begin

Confirm that:

* The required advertising-platform integrations are active.
* Campaign and tactic fields are mapped consistently in the workspace taxonomy.
* The selected model contains the relevant paid media channel or tactic.
* The reporting date range overlaps the model and platform data.

## Accessing Campaign and Creative Views

1. Navigate to **Measure > Models** and select the relevant model.
2. Use the **Contribution** tab for modelled channel and tactic performance.
3. Use the **Creatives** tab, where available, for granular creative and campaign diagnostics.

**[IMAGE PLACEHOLDER: Model workspace showing Contribution and Creatives tabs]**

## Page Filters

Use the available date, platform, channel, tactic, or search controls to narrow the analysis. Keep the selected range consistent when comparing platform metrics with modelled incremental metrics.

## Interpreting Campaign Metrics

### Campaign and Tactic

Campaign identifies the activity reported by the advertising platform. Tactic represents the normalized planning or model grouping configured through Lifesight taxonomy.

### Input Metrics

Input metrics can include spend, impressions, clicks, CPM, CPC, and CTR. These describe the media delivered and the cost of that delivery.

### Platform Outcomes

Platform-reported outcomes, such as platform revenue, orders, ROAS, or CPA, use the attribution rules of the advertising platform. They are useful for operating a channel but should not be treated as incremental by default.

### Incremental Outcomes

Modelled incremental metrics estimate the outcome caused by the marketing activity after accounting for baseline demand, other channels, and contextual factors. Depending on the model KPI, these can include incremental revenue, orders, iROAS, or iCPA.

> 📘 Platform and incremental metrics answer different questions. A difference between them is expected and does not automatically indicate a data error.

## Using Campaign Insights

* Identify campaigns with strong delivery but weak incremental efficiency.
* Compare creative performance within the same channel and objective.
* Review whether a campaign-level pattern is consistent with channel contribution.
* Check data coverage before interpreting missing or unusually low values.
* Use campaign findings to form a testable optimization hypothesis.

**[IMAGE PLACEHOLDER: Campaign or creative table with platform and incremental metrics]**

## Troubleshooting Missing Data

If campaign information is unavailable:

1. Confirm the source integration and account are active.
2. Check taxonomy mappings for platform, channel, tactic, campaign, and creative identifiers.
3. Confirm the date range contains delivered media.
4. Review the model's input and contribution data for the parent channel.
5. Contact Lifesight support if the upstream platform contains data that is not appearing after synchronization.

**[VIDEO PLACEHOLDER: Reviewing campaign and creative performance in Lifesight 4.0]**
