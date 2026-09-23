---
title: Geo Experiment Insights
excerpt: >-
  See the incremental lift your marketing created and know exactly where to
  invest next
deprecated: false
hidden: false
metadata:
  title: Geo Experiment Insights
  keywords:
    - Lifesight Geo Experiment Insights
  robots: noindex
---
Geo Experiment results show you whether your marketing change truly moved your business, and by how much. They compare the observed KPI in treatment markets with a synthetic control (a benchmark built from comparable markets) that estimates what would likely have happened without the treatment, so the difference reflects the real impact of your change.

![](https://files.readme.io/4673d701954cfdb469cc35deac20525cf96cc46538698041d44e14e61caf7e68-Screenshot_2026-09-16_at_3.06.30_PM.png)

## Track your test as it runs

**What you can monitor**

During the experiment, use **Monitoring & Results** to review the following as they become available:

- Progress
- Spend pacing (whether spend is tracking to plan)
- Current lift
- P-value
- Confidence interval
- Power
- Treatment-versus-control trend

**Treat interim results with caution**

Interim results are provisional. They can change as more observations are collected. Avoid ending or extending an experiment based on one interim movement unless the original operating plan allows it. Early swings are common and often settle as the test gathers more data.

![](https://files.readme.io/10c063c3ca209ab0099d60752454aa877979352cfeb5a3ce04e4624c92c69ba0-Screenshot_2026-09-16_at_3.12.36_PM.png)

## Measure lift with updated data

Select **Calculate Lift** when an interim or final analysis is required. Upload updated geographic data that extends the same schema (columns and structure) and granularity used during experiment creation.

**Which data to upload**

- **Interim calculation:** include observations collected through the current experiment date.
- **Final calculation:** at the end of the treatment period, upload the completed treatment-period data.
- **Post-treatment analysis:** when supported, add the required observations after the treatment window before calculating the adjusted result.

**Check your file before submitting**

Check the file's date coverage and geographic fields before submitting it. Gaps, renamed columns, or a different aggregation (such as switching from daily to weekly data) can prevent the updated data from being matched to the experiment.

## Understand what the numbers mean

Each metric answers a different question. Read them together to get the full picture of what your test proved.

**Lift**

Lift is the percentage change in the primary KPI attributed to the treatment. It compares the observed result in treatment markets with the estimated result from the synthetic control.

- **Positive lift:** the treatment markets performed above the estimated baseline.
- **Negative lift:** they performed below the estimated baseline.
- **Lift close to zero:** the measured difference was small.

For example, a lift of 8% means the treatment markets produced approximately 8% more of the selected KPI than the synthetic-control estimate.

**Incremental outcome**

Incremental outcome is the absolute amount of KPI generated above or below the estimated baseline. If the KPI is revenue, this is incremental revenue. If the KPI is orders, this is incremental orders.

Use lift for the relative change and incremental outcome for the business magnitude. An 8% lift sounds strong, but the incremental outcome tells you whether it amounts to $5,000 or $500,000.

**iROAS**

Incremental Return on Ad Spend shows how much incremental revenue was generated for each unit of incremental media spend.

For example, an iROAS of 1.50x means the experiment measured $1.50 in incremental revenue for every $1.00 of incremental spend. Review iROAS with its lift, uncertainty, and profit requirements before deciding whether the result is commercially attractive.

**P-value**

The p-value indicates how compatible the observed result is with a scenario where the treatment had no effect. A smaller p-value provides stronger statistical evidence against that no-effect scenario.

Compare the p-value with the significance level selected in the experiment design. A result can be commercially meaningful without reaching the target, but the evidence is less conclusive.

**Statistically Significant**

This card summarizes whether the result meets the configured statistical threshold:

- **Yes:** the threshold was met.
- **Almost:** emerging evidence that has not yet met the configured threshold.
- **No:** the current evidence is not strong enough.

Statistical significance does not describe the size or profitability of the effect. Review **Lift** and **iROAS** as well.

**Confidence interval**

The confidence interval shows a plausible range around the lift estimate at the configured confidence level.

- **A narrower interval** means the estimate is more precise.
- **An interval that excludes zero** supports a statistically significant positive or negative result.
- **An interval that crosses zero** means the data is also compatible with little or no effect.

**Statistical power**

Power is the probability that the experiment design will detect an effect of the planned size when that effect is real. Power builds as the experiment collects useful observations.

Low power means a non-significant result may be inconclusive rather than evidence that the treatment had no effect.

**Minimum Detectable Lift**

Minimum Detectable Lift, or MDE, is the smallest lift the design is expected to detect reliably. A design with an MDE of 10% may not reliably identify a true lift of 4%.

Use MDE during design to check whether the experiment can answer the business question at a useful level of sensitivity.

**Adjusted Lift and Adjusted iROAS**

Adjusted metrics appear when post-treatment analysis is available. They incorporate the additional observation window after treatment and help show whether measured effects persisted beyond the experiment window.

Compare the main and adjusted results rather than replacing one with the other. A material difference can indicate a delayed response (impact that showed up after the test ended) or post-treatment decay (impact that faded once the treatment stopped).

## See where the result comes from

**Treatment versus control**

The trend chart compares the treatment markets with the synthetic control over time. Before treatment, the lines should track closely, which shows the control is a credible benchmark. During treatment, a sustained separation between the lines can support the measured lift.

**Cell breakdown**

For a multi-cell experiment, review spend, lift, iROAS, p-value, and confidence for each cell. A strong blended result can hide meaningful differences between treatments. For example, one cell may be driving most of the lift while another shows no effect.

**Market breakdown**

Use the market table to identify where the result is concentrated. One unusually strong or weak market can influence the overall estimate and should be checked against local events or data issues, such as a regional promotion or a tracking outage.

**Entity retrospective**

The entity retrospective shows how selected campaigns behaved during the test, including spend against plan and geographic execution. Use it to confirm that the treatment was implemented as designed. If campaigns didn't run as planned, the result may not reflect the change you intended to test.

**\[IMAGE PLACEHOLDER: Result cards, treatment-versus-control chart, and cell or market breakdown]**

## Read completed results in the right order

Use this order when interpreting a completed experiment:

1. **Confirm execution.** Check that campaign execution and spend followed the plan.
2. **Review business impact.** Look at **Lift** and incremental outcome.
3. **Review efficiency.** Check **iROAS** for incremental efficiency.
4. **Check uncertainty.** Review the p-value and confidence interval.
5. **Check consistency.** Review cell and market breakdowns for concentration or inconsistency.
6. **Compare adjusted results** when post-treatment analysis is available.
7. **Connect it back to your question.** Read the findings, recommendation, and conclusion with the original hypothesis.

**Note:** A non-significant result does not automatically prove that there was no effect. The experiment may have measured a small effect, collected insufficient information, or had more variation than the design expected.

## Put credible results to work

Promote an experiment when its design, execution, and result are credible enough to support downstream measurement. A promoted experiment can inform Attribution and eligible model-calibration workflows, anchoring your other measurement to a proven real-world result.

**Review before promoting**

Promotion is not a substitute for review. Before promoting, confirm the result against:

- The original hypothesis
- Effect size
- Uncertainty
- Power
- Market consistency
- Campaign execution

## Revisit the original design

Open **Design of Experiment** to revisit the hypothesis, treatment, cells, KPI definitions, date windows, selected markets, power analysis, MDE, and synthetic-control fit. Interpret the result against the question and assumptions defined before the experiment began, so your conclusion answers the question you actually set out to test.

***

## Frequently Asked Questions

**Can I check results while the experiment is still running?**
Yes. **Monitoring & Results** shows progress, spend pacing, current lift, p-value, confidence interval, power, and the treatment-versus-control trend when available. Treat these interim results as provisional.

**Should I stop my test early if results look strong?**
Avoid ending or extending an experiment based on one interim movement unless your original operating plan allows it. Interim results can change as more data comes in.

**What data do I upload to calculate lift?**
Upload updated geographic data that extends the same schema and granularity used during experiment creation. Include data through the current date for an interim result, or the completed treatment period for a final result.

**Why won't my updated data match the experiment?**
Gaps in dates, renamed columns, or a different aggregation can prevent matching. Check date coverage and geographic fields before submitting.

**What is the difference between lift and incremental outcome?**
Lift is the relative percentage change. Incremental outcome is the absolute amount, such as incremental revenue or orders. Use both to understand the size of the impact.

**What does an iROAS of 1.50x mean?**
The experiment measured $1.50 in incremental revenue for every $1.00 of incremental spend.

**What does "Almost" mean on the Statistically Significant card?**
There is emerging evidence, but it has not met the configured statistical threshold.

**Does a statistically significant result mean the change was profitable?**
No. Statistical significance only tells you how strong the evidence is. Review **Lift** and **iROAS** to understand the size and profitability of the effect.

**Does a non-significant result mean my marketing had no effect?**
Not necessarily. The effect may have been small, the test may not have collected enough information, or there may have been more variation than expected. Check power and MDE to understand whether the test could have detected the effect.

**What are Adjusted Lift and Adjusted iROAS?**
They incorporate an additional observation window after treatment, showing whether effects persisted beyond the test. Compare them with the main results rather than replacing them.

**Why should I review the market breakdown?**
One unusually strong or weak market can influence the overall result. Check any outliers against local events or data issues.

**When should I promote an experiment?**
When its design, execution, and result are credible. Confirm the result against the original hypothesis, effect size, uncertainty, power, market consistency, and campaign execution first.

**What happens after I promote a result?**
A promoted experiment can inform Attribution and eligible model-calibration workflows.