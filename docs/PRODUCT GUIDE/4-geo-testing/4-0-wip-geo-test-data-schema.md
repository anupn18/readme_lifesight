---
title: '[4.0][WIP] Geo test data schema'
excerpt: Lifesight 4.0 WIP guide for Geo test data schema.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
**Prepare Your Data for Reliable Geo Experiment Results**

Map your historical data correctly so Lifesight can build accurate market comparisons and measure the true incremental impact of your marketing. The Data step lets you bring in your data, match each column to the right field, and confirm everything is ready before you design your test.

![](https://files.readme.io/87b7e7c8cf9ab5d355b60ed5df757a32601903b5459c1d0f97ec6b4075810f89-Screenshot_2026-09-16_at_3.46.56_PM.png)

### Set up the required fields to measure lift

Lifesight needs these settings and column mappings to compare your markets and measure incremental results accurately. Continue to design stays unavailable until they are complete.

**Data settings**

| Field                    | What it controls                                           |            |
| ------------------------ | ---------------------------------------------------------- | ---------- |
| **Primary KPI**          | The metric you will measure lift on                        | Revenue    |
| **Date format**          | How dates are written in your data                         | yyyy-mm-dd |
| **Date Granularity**     | How often your data is reported                            | Daily      |
| **Pre-Treatment Period** | The historical baseline window used before the test starts | 12 months  |
| **Region Granularity**   | The geographic level markets are matched at                | State      |

**Column mapping**

| **Field**       | What to select                                                                                                  | Example column |
| --------------- | --------------------------------------------------------------------------------------------------------------- | -------------- |
| **Date Column** | The column that holds your observation dates                                                                    | date           |
| **KPI Column**  | The column for your primary KPI. The label updates to match the KPI you chose (for example, **Revenue Column**) | revenue        |
| **Geo**         | The column that holds your market names, at the region granularity you selected                                 | state          |

**Add optional fields for deeper insights**

| Field          | What it adds                                                                                                        | Example column |
| -------------- | ------------------------------------------------------------------------------------------------------------------- | -------------- |
| Parent Geo     | The larger region each market belongs to, such as the state for a city                                              | state          |
| Spend Column   | Cost context, so you can evaluate efficiency metrics such as iROAS alongside lift                                   | spend          |
| Secondary KPIs | Additional outcomes to track beyond your primary KPI. Click Add KPI, choose the KPI, and select its matching column | spend          |

Parent geo fields become required for granularities that need geographic hierarchy. The mapping interface identifies **Parent Geo 1** and **Parent Geo 2** when applicable.

**Supported KPIs**<br /><br />Primary KPI: Revenue, Conversions, ROAS, CPA, and Orders (revenue)<br />Secondary KPIs: Revenue, Conversions, ROAS, CPA, Orders, New customers, AOV, and Sessions

### Formatting requirements

- Use a single header row with unique column names.
- Keep date format and daily or weekly granularity consistent.
- Include repeated dates for each market represented in the observation period.
- Use numeric values for KPI and spend fields.
- Avoid merged cells, totals rows, formatted titles, and blank header names.
- Keep geo labels consistent across the complete pre-treatment period.

### Pre-treatment coverage

Provide sufficient history for synthetic-control fitting. The creation flow supports preset pre-treatment periods and custom values from 1 to 24 months.

Review the detected file preview and mappings before continuing to Design.
