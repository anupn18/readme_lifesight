---
title: '[4.0][WIP] Create and Design a Geo Experiment'
excerpt: Build a geo test that turns market results into confident budget decisions.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Geo Experiments show you the true incremental impact of your marketing, so you can see which changes actually drive results and invest with confidence.

Platform-reported metrics tell you what happened after someone saw an ad, but not whether the ad caused it. Some of those conversions would have happened anyway. A geo experiment answers the question that matters most: how much additional revenue, conversions, or new customers did this marketing change create?

Create a Geo Experiment from the Experiments workspace to measure the incremental effect of a marketing change across selected geographic markets.

![](https://files.readme.io/6b273c68050038b886cb89a9465396e6fdd8d13b5693fa4a2196bb810d9d3fe0-Screenshot_2026-09-16_at_2.26.14_PM.png)

## Before you begin

Prepare a CSV with a date column, a geographic-market column, and the primary KPI you want to measure. You should also know the channel or tactic you want to test, the expected incremental efficiency, and any markets that must be included or excluded.

## Start a Geo Experiment

1. Select **Experiments** from the sidebar.
2. Select **New Experiment**.
3. Choose **Geo Testing**.

![](https://files.readme.io/df37e817fde4c16316095eeffca092222d487c99fa42b06a84cab6135ebb3e4d-Screenshot_2026-09-16_at_2.26.52_PM.png)

The creation workflow has three steps: **Goal**, **Data**, and **Design**. You can save an incomplete experiment as a draft and resume it from the Experiment List.

![](https://files.readme.io/ce2bf88868c6dd2d39ced4d32dae31cd75099b36c339824af317ac7d1f19f99f-Screenshot_2026-09-16_at_2.27.09_PM.png)

## 1. Define the goal

Enter a unique experiment name, then select a saved hypothesis or write your own. A clear hypothesis states what you are changing, where you expect an effect, and which KPI should respond.

Choose the treatment type:

* **Hold-out:** Pause selected media activity in the test markets to measure what would have happened without it.
* **Scale-up:** Increase media activity in the test markets to measure the incremental response from additional investment.

![](https://files.readme.io/007be217703cf6ca5486ca060986045ce8e805c1248d324ad9c2cd4bc9f7789c-Screenshot_2026-09-16_at_2.27.55_PM.png)

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

![](https://files.readme.io/d827aacca9d83f560c446fb3a63b95fe9539b59dae0b25052cf40df3f13c2bd6-Screenshot_2026-09-16_at_2.28.42_PM.png)

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

**\[IMAGE PLACEHOLDER: Design step with test cells, duration, market count, and advanced settings]**

## Find and compare markets

Select **Find markets** to submit the design. Lifesight evaluates candidate test markets and builds a weighted synthetic control for each recommendation.

Review:

* **Synthetic-control fit:** How closely the control reproduces the test markets before treatment. A closer pre-treatment fit provides a more credible baseline.
* **Statistical power:** The likelihood that the design can detect an effect of the planned size when the effect is real. Higher power is preferable.
* **Minimum Detectable Lift:** The smallest lift the design is expected to detect reliably. Lower values allow the experiment to identify smaller effects.
* **Estimated investment:** The additional or withheld spend associated with the design.
* **Control weights:** How much each control market contributes to the synthetic-control baseline.

Choose a recommendation that balances statistical quality with operational feasibility. Avoid selecting a market combination on investment alone.

**\[IMAGE PLACEHOLDER: Recommended test markets with fit chart, power analysis, MDE, and control weights]**

## Select campaigns and schedule

After selecting the test markets, choose eligible campaigns for each cell.

* For a Hold-out, select the campaigns or ad sets to exclude from the test markets.
* For a Scale-up, select the control campaigns that your team will duplicate into test campaigns.

Choose the start date and deployment method, then promote and schedule the experiment when every cell is ready.

<Callout icon="📘" theme="info">
  ### Automatic campaign scheduling may not be available for every workflow. With Manual deployment, your team must apply the planned changes in the advertising platform on the scheduled date.
</Callout>

**\[VIDEO PLACEHOLDER: Reviewing markets, selecting campaigns, and scheduling a Geo Experiment]**

## Final checklist

Before scheduling, confirm that:

* The hypothesis and primary KPI match the business decision.
* The test and pre-treatment windows are correct.
* The selected markets have an acceptable fit, power, and MDE.
* Campaign ownership and deployment steps are clear.
* No unrelated market-level activity is expected to distort the test.
