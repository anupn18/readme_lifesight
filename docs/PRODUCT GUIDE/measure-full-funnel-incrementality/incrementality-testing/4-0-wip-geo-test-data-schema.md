---
title: '[4.0][WIP] Geo test data schema'
excerpt: Lifesight 4.0 WIP guide for Geo test data schema.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Geo Test Data Schema

Lifesight 4.0 accepts a CSV upload for Geo Experiment creation. The file can be up to 200 MB and must include a header row.

[IMAGE PLACEHOLDER: Geo Experiment CSV upload and column mapping]

## Required fields

| Field | Description |
| --- | --- |
| Date | Observation date using one consistent format |
| Geo | Market at the selected region granularity |
| Primary KPI | Numeric outcome used to measure lift |

Parent geo fields become required for granularities that need geographic hierarchy. The mapping interface identifies **Parent Geo 1** and **Parent Geo 2** when applicable.

## Optional fields

- Spend
- Secondary KPI columns
- Parent geo fields when not required by the selected granularity

Supported primary KPI labels include Revenue, Conversions, ROAS, CPA, and Orders (revenue). Secondary KPIs can include Revenue, Conversions, ROAS, CPA, Orders, New customers, AOV, and Sessions.

## Formatting requirements

- Use a single header row with unique column names.
- Keep date format and daily or weekly granularity consistent.
- Include repeated dates for each market represented in the observation period.
- Use numeric values for KPI and spend fields.
- Avoid merged cells, totals rows, formatted titles, and blank header names.
- Keep geo labels consistent across the complete pre-treatment period.

[VIDEO PLACEHOLDER: Uploading a CSV and mapping date, geo, and KPI columns]

## Pre-treatment coverage

Provide sufficient history for synthetic-control fitting. The creation flow supports preset pre-treatment periods and custom values from 1 to 24 months.

Review the detected file preview and mappings before continuing to Design.
