---
title: '[4.0][WIP] Custom Budget Pacing'
excerpt: Lifesight 4.0 WIP guide for Custom Budget Pacing.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Custom Budget Pacing

Custom pacing distributes a scenario's planned budget across individual months and applies month-specific channel constraints.

[IMAGE PLACEHOLDER: Advanced Configuration Custom Pacing tab]

## When to use custom pacing

Use custom pacing when spend should not be distributed uniformly across the plan period. Common reasons include seasonality, launches, promotions, inventory limits, or contractual media commitments.

## Configure custom pacing

1. Open a Planner scenario.
2. Select **Advanced Config**.
3. Open **Custom Pacing**.
4. Review current and planned budget by month.
5. Edit monthly budgets or upload a pacing plan.
6. Review channel constraints for each month.
7. Confirm that monthly budgets add up to the total planned budget.
8. Select **Apply** or **Done**, then run the simulation.

[VIDEO PLACEHOLDER: Editing monthly pacing and channel constraints]

## Monthly allocation rules

Unmodified months divide the remaining planned budget using current monthly spend when it is available. Otherwise, the remainder is divided evenly. The final unmodified month absorbs rounding so the total matches the planned budget.

Each month's channel bounds are scaled from that month's planned budget and sent as constraints for that period.

## Validation

Every monthly budget must be greater than zero, remain within allowed limits, and sum to the total planned budget. Channel minimums cannot be negative or exceed their maximums.

[IMAGE PLACEHOLDER: Custom pacing validation and allocated total]

If using an upload, start from the provided template and keep the CSV under the platform's stated file-size limit.
