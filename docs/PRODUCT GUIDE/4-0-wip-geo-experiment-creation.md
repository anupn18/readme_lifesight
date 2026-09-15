---
title: '[4.0][WIP] Create and Design a Geo Experiment'
excerpt: Lifesight 4.0 WIP guide for Geo test creation.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Create and Design a Geo Experiment

Create a Geo Experiment from the Experiments workspace to measure the incremental effect of a marketing change across selected geographic markets.

**[IMAGE PLACEHOLDER: New Experiment button in the Experiment List]**

## Before you begin

Prepare a CSV with a date column, a geographic-market column, and the primary KPI you want to measure. You should also know the channel or tactic you want to test, the expected incremental efficiency, and any markets that must be included or excluded.

## Start a Geo Experiment

1. Select **Experiments** from the sidebar.
2. Select **New Experiment**.
3. Choose **Geo Testing**.

The creation workflow has three steps: **Goal**, **Data**, and **Design**. You can save an incomplete experiment as a draft and resume it from the Experiment List.

**[VIDEO PLACEHOLDER: Creating a Geo Experiment in the three-step wizard]**

## 1. Define the goal

Enter a unique experiment name, then select a saved hypothesis or write your own. A clear hypothesis states what you are changing, where you expect an effect, and which KPI should respond.

Choose the treatment type:

* **Hold-out:** Pause selected media activity in the test markets to measure what would have happened without it.
* **Scale-up:** Increase media activity in the test markets to measure the incremental response from additional investment.

**[IMAGE PLACEHOLDER: Goal step with name, hypothesis, and treatment type]**

## 2. Add and map the data

Upload the experiment CSV, then configure:

* Primary KPI
* Date field and date format
* Daily or weekly data granularity
* Geographic field and region granularity
* Pre-treatment period
* Optional spend and secondary KPI fields

The pre-treatment period gives Lifesight the history needed to build a synthetic control. Use a continuous period that represents normal business behavior and includes enough variation to distinguish test markets from their controls.

See **Geo test data schema** for file requirements and formatting guidance.

**[IMAGE PLACEHOLDER: Data step with date, geography, KPI, and optional field mappings]**

## 3. Configure the design

Create one or more test cells. Each cell represents a treatment that will be measured within the experiment.

For each cell, enter:

* A clear cell name
* Channel and tactic
* Target iROAS or iCPA
* Candidate test durations
* Candidate numbers of test markets

Advanced settings can include the lift model, lookback window, fixed effects, significance level, additional budget, expected effect range, and markets to include or exclude.

Use realistic target efficiency and effect assumptions. An aggressive target can make a design look inexpensive while reducing the chance that the expected effect can be detected.

**[IMAGE PLACEHOLDER: Design step with test cells, duration, market count, and advanced settings]**

## Find and compare markets

Select **Find markets** to submit the design. Lifesight evaluates candidate test markets and builds a weighted synthetic control for each recommendation.

Review:

* **Synthetic-control fit:** How closely the control reproduces the test markets before treatment. A closer pre-treatment fit provides a more credible baseline.
* **Statistical power:** The likelihood that the design can detect an effect of the planned size when the effect is real. Higher power is preferable.
* **Minimum Detectable Lift:** The smallest lift the design is expected to detect reliably. Lower values allow the experiment to identify smaller effects.
* **Estimated investment:** The additional or withheld spend associated with the design.
* **Control weights:** How much each control market contributes to the synthetic-control baseline.

Choose a recommendation that balances statistical quality with operational feasibility. Avoid selecting a market combination on investment alone.

**[IMAGE PLACEHOLDER: Recommended test markets with fit chart, power analysis, MDE, and control weights]**

## Select campaigns and schedule

After selecting the test markets, choose eligible campaigns for each cell.

* For a Hold-out, select the campaigns or ad sets to exclude from the test markets.
* For a Scale-up, select the control campaigns that your team will duplicate into test campaigns.

Choose the start date and deployment method, then promote and schedule the experiment when every cell is ready.

> 📘 Automatic campaign scheduling may not be available for every workflow. With Manual deployment, your team must apply the planned changes in the advertising platform on the scheduled date.

**[VIDEO PLACEHOLDER: Reviewing markets, selecting campaigns, and scheduling a Geo Experiment]**

## Final checklist

Before scheduling, confirm that:

* The hypothesis and primary KPI match the business decision.
* The test and pre-treatment windows are correct.
* The selected markets have an acceptable fit, power, and MDE.
* Campaign ownership and deployment steps are clear.
* No unrelated market-level activity is expected to distort the test.
