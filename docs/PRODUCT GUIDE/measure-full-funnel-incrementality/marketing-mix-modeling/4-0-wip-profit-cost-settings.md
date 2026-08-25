---
title: '[4.0][WIP] Profit & Cost Settings'
excerpt: Configure cost assumptions for profit-based MMM metrics.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Cost Settings define the financial assumptions used to calculate incremental profit, incremental profit margin, iPOAS, and LTV-to-CPA metrics in Lifesight 4.0.

## Accessing Cost Settings

1. Navigate to **Configurations > Cost Settings**.
2. Select the period you want to configure.
3. Review default, channel, model-type, and custom cost scopes.

**[IMAGE PLACEHOLDER: Cost Settings page showing the shared month window and cost scopes]**

## Monthly Cost Assumptions

Cost assumptions are configured by month. All sections use the same month window, so adding or removing a month updates the period shown across the page.

You can enter values for an individual month or fill a larger period where the same assumption applies.

## Cost Scopes

### Default Costs

Default costs apply when a more specific channel or model-type value is not configured. Use them for assumptions shared across the business.

### Channel Costs

Create a channel scope when a standard cost differs for one media channel. Select the channel, calculation type, and the cost fields that should be tracked.

### Model-Type Costs

Use a model-type scope when an assumption should apply only to a particular measurement model or business outcome.

### Custom Costs

Add custom costs for financial inputs that are not covered by the standard cost types. Use a clear description so reviewers understand what the value represents and where it applies.

## Common Financial Inputs

Depending on the configured calculation, cost settings can include:

* Cost of goods sold
* Fixed or variable operating costs
* Channel-specific fees
* Average order value
* Customer lifetime value and its reporting horizon

> 📘 Customer lifetime value supports the LTV-to-CPA ratio. It is not automatically subtracted from incremental profit.

## How Costs Affect Model Reporting

For revenue and profit outcomes, the **Contribution** tab can show:

* Incremental profit
* Incremental profit margin
* Incremental profit on ad spend
* LTV-to-CPA ratio where applicable

These values use the active cost assumptions for the selected channel and period. Review cost settings when a profit metric appears unexpected or unavailable.

**[IMAGE PLACEHOLDER: Contribution table showing incremental profit and margin columns]**

## Best Practices

* Keep monthly assumptions aligned with finance-approved values.
* Use channel scopes only when a channel genuinely differs from the default.
* Document custom costs clearly.
* Review the month window before saving.
* Revisit assumptions when prices, margins, fees, or customer value change.
* Confirm cost coverage before using profit as a Planner goal.

**[VIDEO PLACEHOLDER: Configuring cost assumptions for MMM profit reporting]**
