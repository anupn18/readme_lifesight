---
title: '[4.0][WIP] Geo Experiment Design'
excerpt: Lifesight 4.0 WIP guide for Geo Experiment Design.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Geo Experiment Design

The Lifesight 4.0 Geo Experiment workflow has three steps: **Goal**, **Data**, and **Design**. After submission, Lifesight searches for recommended test markets.

[IMAGE PLACEHOLDER: Geo Experiment three-step wizard]

## 1. Goal

Enter a unique experiment name, then select a predefined hypothesis or write your own. Examples include testing whether a channel is working, evaluating a scale-up, comparing channels, validating an MMM recommendation, or testing a creative or audience strategy.

Choose the supported treatment:

- **Hold-out** to pause spend in test markets
- **Scale-up** to increase spend in test markets

[IMAGE PLACEHOLDER: Goal step with hypothesis and treatment]

## 2. Data

Upload a CSV with date, geo, and KPI columns. Configure the primary KPI, date format, daily or weekly granularity, pre-treatment period, and region granularity. Map required columns and add optional spend or secondary KPI columns.

[IMAGE PLACEHOLDER: Data step with CSV column mapping]

## 3. Design

Configure one or more test cells. For each cell, provide a title, channel, tactic, and target iROAS. Select candidate durations and test-market counts.

Advanced settings can include the lift model, lookback window, fixed effects, significance level, additional budget, effect range, and markets to include or exclude.

[IMAGE PLACEHOLDER: Design step with cells and advanced settings]

## Find markets

Select **Find markets** to submit the design. Lifesight evaluates synthetic-control fit, power, and candidate market combinations. Review the recommended test markets, power analysis, fit chart, and control weights before scheduling.

[VIDEO PLACEHOLDER: Completing a design and reviewing market recommendations]

You can save an incomplete experiment as a draft and resume it from the Experiment List.
