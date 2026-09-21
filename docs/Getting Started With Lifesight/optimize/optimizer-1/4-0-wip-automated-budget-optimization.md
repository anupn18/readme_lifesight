---
title: '[4.0][WIP] Automated Budget Optimization'
excerpt: Lifesight 4.0 WIP guide for Automated Budget Optimization.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Automated Budget Optimization

In Lifesight 4.0, budget recommendations are created in Planner and implemented from **Deploy** after a scenario is promoted to Decisions.

[IMAGE PLACEHOLDER: Deploy workspace with promoted scenario summary]

## Before you begin

Create, run, save, and promote a Planner scenario. Deploy shows an empty state until a plan is promoted.

Review the promoted scenario's planned budget, forecasted outcome, forecasted iROAS or iCPA, constraints, and channel recommendations before applying changes.

## Review deployment recommendations

Deploy summarizes:

- Planned budget compared with current budget
- Forecasted revenue or selected outcome
- Forecasted incremental efficiency
- Budget pacing over the forecast horizon
- Campaign, ad set, and creative recommendations

[IMAGE PLACEHOLDER: Deploy summary metrics and campaign table]

## Apply budget recommendations

1. Open **Deploy**.
2. Select **Campaigns** or **Ad Sets**.
3. Review current and recommended budgets, pacing, and warnings.
4. Open the row action or select multiple eligible entities.
5. Choose **Change Budget**.
6. Select **Recommended** to apply engine values or **Custom** to enter values manually.
7. Review cautions and excluded entities.
8. Select **Apply Budget Change**.

[VIDEO PLACEHOLDER: Applying recommended budgets to selected campaigns]

## Other supported actions

Depending on platform support and permissions, Deploy can change bid values and campaign status. Geo changes are available for supported experiment deployment workflows.

## Verify changes

Open **Logs** to review the platform action, user, entity, previous value, new value, status, and timestamp.

> Applying a recommendation changes connected advertising-platform state. Review permissions, warnings, and operational timing before confirmation.
