---
title: '[4.0][WIP] Geo Experiment Insights'
excerpt: Lifesight 4.0 WIP guide for Geo Experiment Insights.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Geo Experiment Insights

Geo Experiment results compare the observed KPI in treatment markets with a synthetic control that estimates what would likely have happened without the treatment.

**[IMAGE PLACEHOLDER: Monitoring & Results tab for a Geo Experiment]**

## Monitor a running experiment

During the experiment, use **Monitoring & Results** to review progress, spend pacing, current lift, p-value, confidence interval, power, and the treatment-versus-control trend when those results are available.

Interim results are provisional. They can change as more observations are collected. Avoid ending or extending an experiment based on one interim movement unless the original operating plan allows it.

**[VIDEO PLACEHOLDER: Reviewing experiment progress and interim results]**

## Calculate lift

Select **Calculate Lift** when an interim or final analysis is required. Upload updated geographic data that extends the same schema and granularity used during experiment creation.

For an interim calculation, include observations collected through the current experiment date. At the end of the treatment period, upload the completed treatment-period data to calculate the final result. When post-treatment analysis is supported, add the required observations after the treatment window before calculating the adjusted result.

Check the file's date coverage and geographic fields before submitting it. Gaps, renamed columns, or a different aggregation can prevent the updated data from being matched to the experiment.

**[VIDEO PLACEHOLDER: Uploading updated geographic data and calculating lift]**

## Understand the main metrics

### Lift

Lift is the percentage change in the primary KPI attributed to the treatment. It compares the observed result in treatment markets with the estimated result from the synthetic control.

* Positive lift means the treatment markets performed above the estimated baseline.
* Negative lift means they performed below the estimated baseline.
* Lift close to zero means the measured difference was small.

Example: A lift of 8% means the treatment markets produced approximately 8% more of the selected KPI than the synthetic-control estimate.

### Incremental outcome

Incremental outcome is the absolute amount of KPI generated above or below the estimated baseline. If the KPI is revenue, this is incremental revenue. If the KPI is orders, this is incremental orders.

Use lift for the relative change and incremental outcome for the business magnitude.

### iROAS

Incremental Return on Ad Spend shows how much incremental revenue was generated for each unit of incremental media spend.

For example, an iROAS of `1.50x` means the experiment measured 1.50 in incremental revenue for every 1.00 of incremental spend. Review iROAS with its lift, uncertainty, and profit requirements before deciding whether the result is commercially attractive.

### P-value

The p-value indicates how compatible the observed result is with a scenario where the treatment had no effect. A smaller p-value provides stronger statistical evidence against that no-effect scenario.

Compare the p-value with the significance level selected in the experiment design. A result can be commercially meaningful without reaching the target, but the evidence is less conclusive.

### Statistically Significant

This card summarizes whether the result meets the configured statistical threshold. **Yes** means the threshold was met. **Almost** indicates emerging evidence that has not met the configured threshold. **No** means the current evidence is not strong enough.

Statistical significance does not describe the size or profitability of the effect. Review Lift and iROAS as well.

### Confidence interval

The confidence interval shows a plausible range around the lift estimate at the configured confidence level.

* A narrower interval means the estimate is more precise.
* An interval that excludes zero supports a statistically significant positive or negative result.
* An interval that crosses zero means the data is also compatible with little or no effect.

### Statistical power

Power is the probability that the experiment design will detect an effect of the planned size when that effect is real. Power builds as the experiment collects useful observations.

Low power means a non-significant result may be inconclusive rather than evidence that the treatment had no effect.

### Minimum Detectable Lift

Minimum Detectable Lift, or MDE, is the smallest lift the design is expected to detect reliably. A design with an MDE of 10% may not reliably identify a true lift of 4%.

Use MDE during design to check whether the experiment can answer the business question at a useful level of sensitivity.

### Adjusted Lift and Adjusted iROAS

Adjusted metrics appear when post-treatment analysis is available. They incorporate the additional observation window after treatment and help show whether measured effects persisted beyond the experiment window.

Compare the main and adjusted results rather than replacing one with the other. A material difference can indicate delayed response or post-treatment decay.

## Read the charts and breakdowns

### Treatment versus control

The trend chart compares the treatment markets with the synthetic control over time. Before treatment, the lines should track closely. During treatment, a sustained separation can support the measured lift.

### Cell breakdown

For a multi-cell experiment, review spend, lift, iROAS, p-value, and confidence for each cell. A strong blended result can hide meaningful differences between treatments.

### Market breakdown

Use the market table to identify where the result is concentrated. One unusually strong or weak market can influence the overall estimate and should be checked against local events or data issues.

### Entity retrospective

The entity retrospective shows how selected campaigns behaved during the test, including spend against plan and geographic execution. Use it to confirm that the treatment was implemented as designed.

**[IMAGE PLACEHOLDER: Result cards, treatment-versus-control chart, and cell or market breakdown]**

## Review completed results

Use this order when interpreting a completed experiment:

1. Confirm that campaign execution and spend followed the plan.
2. Review Lift and incremental outcome for business impact.
3. Review iROAS for incremental efficiency.
4. Check the p-value and confidence interval for uncertainty.
5. Review cell and market breakdowns for concentration or inconsistency.
6. Compare adjusted results when post-treatment analysis is available.
7. Read the findings, recommendation, and conclusion with the original hypothesis.

> 📘 A non-significant result does not automatically prove that there was no effect. The experiment may have measured a small effect, collected insufficient information, or had more variation than the design expected.

## Promote a result

Promote an experiment when its design, execution, and result are credible enough to support downstream measurement. A promoted experiment can inform Attribution and eligible model-calibration workflows.

Promotion is not a substitute for review. Confirm the result against the original hypothesis, effect size, uncertainty, power, market consistency, and campaign execution before promoting it.

## Review the original design

Open **Design of Experiment** to revisit the hypothesis, treatment, cells, KPI definitions, date windows, selected markets, power analysis, MDE, and synthetic-control fit. Interpret the result against the question and assumptions defined before the experiment began.

**[VIDEO PLACEHOLDER: Interpreting lift, iROAS, significance, and confidence together]**