---
title: '[4.0][WIP] Refresh Indicators'
excerpt: Lifesight 4.0 WIP guide for Refresh Indicators.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Refresh Indicators

The Attribution header in Lifesight 4.0 shows a **Last updated** indicator for the causal attribution response.

[IMAGE PLACEHOLDER: Last updated indicator in the Attribution header]

## Read the indicator

The status dot and timestamp show the freshness of the Attribution data currently displayed. A fresh status indicates that the latest expected result is available. A warning status indicates that the result may be stale.

The 4.0 workspace does not display the two separate legacy indicators for Platform Data and Attribution Data.

## If data appears stale

1. Confirm the selected date range.
2. Go to **Integrations** and review the status of connected advertising platforms.
3. Confirm that required Marketing Mix Models, experiments, and scenarios are available and promoted where needed.
4. Refresh the page after the upstream data has completed processing.

[VIDEO PLACEHOLDER: Checking Attribution freshness and reviewing Integrations]

## No data state

If Attribution shows no data, the workspace may not have a configured attribution data pipeline or the selected period may not contain results. Check integration and measurement setup, then contact your Lifesight support representative if the issue continues.

> A recent timestamp confirms freshness of the displayed result. It does not replace validation of source integrations or measurement quality.
