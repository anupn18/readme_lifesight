---
title: Target benchmark
excerpt: >-
  Get automated budget recommendations to optimize campaigns and ad sets based
  on the Target Benchmark
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Target Benchmark allows you to set a primary marketing goal - such as maximizing revenue or minimizing Cost Per Acquisition (CPA) - and receive data-driven budget allocation recommendations to achieve it.

### How to Set a Target Benchmark

Applying a benchmark is a straightforward process from the main Attribution dashboard.

1. Navigate to the **Attribution** section of the platform.
2. Click the **Target [Benchmark Name/Metric]** button located at the top-right corner of the dashboard

   <Image align="center" width="650px" src="https://files.readme.io/db2cb483984e5b74857ecf8501098bd5c4b1353411256d78f9fa83c4c0681921-Attribution_-_Target_Benchmark_highlighted.png" />
3. In the **Target** modal that appears, use the **Select a Metric** dropdown to choose your desired benchmark.

   <Image align="center" width="400px" src="https://files.readme.io/283445a7d0915e68766c670b8c60a9b49854e984d9cf83b0c3c2a02ca5989b49-Target_Benchmark_-_dropdown_menu_.png" />
4. Click **Confirm** to apply the benchmark. The Channel Breakdown table will refresh with specific recommendations.

***

### Understanding Recommendations for Causal Attribution

<Callout icon="📘" theme="info">
  When using  **Causal** attribution, the Target Benchmark feature provides **quantifiable** budget recommendations.
</Callout>

Because Causal models are powered by Lifesight's advanced Marketing Mix Models and experiments, the platform can calculate the precise budget adjustments needed to meet your goals.

<Image align="center" src="https://files.readme.io/4b7368af47da073045f92c164e27206ff36122fc7125ecbe2e8b00a41ceda17f-Causal_Attribution_Recommendations.png" />

#### Benchmark Options for Causal Models

You can set the following types of targets:

* **Forecasted Scenarios:** Select a pre-configured business forecast that has been set as a default scenario (e.g., 'BFCM-Q4-Forecast').
* **Incremental Metrics:** Target a specific incremental ROAS (iROAS) or incremental Cost Per Action (iCPA) to optimize for true business lift.
* **Marginal Metrics:** Set a goal for marginal ROAS (mROAS) or marginal CPA (mCPA) to ensure the efficiency of your next marketing dollar spent.

<br />

#### Interpreting Causal Recommendations

The recommendations will appear with specific dollar amounts, advising you exactly how much to increase or decrease spend in a channel to reach your target.

***

### Understanding Recommendations for Touch-Based Attribution

<Callout icon="📘" theme="info">
  When using touch-based attribution models (e.g., Time Decay, Last Touch), the recommendations provided are **directional**.
</Callout>

These models evaluate channel performance relative to your target and provide guidance on how to shift budgets, rather than prescribing exact amounts.

<Image align="center" src="https://files.readme.io/15b4ca4cfa804d28fc5ac326cc6fa49ba80fcde36a33f333cb0dd782b93580ba-Touch-based_attribution_recommendations.png" />

#### Benchmark Options for Touch-Based Models

You will typically select a standard marketing metric and set a specific value as the target (e.g., Target ROAS 3.7).

#### Interpreting Directional Recommendations

The recommendations guide your strategy with the following labels:

* **Scale up:** Indicates that the channel is performing efficiently against the target and has room to absorb more budget.
* **Reduce:** Suggests the channel is underperforming relative to the target, and funds could be reallocated to more efficient channels.
* **Maintain:** The channel is performing as expected, and the current budget level is appropriate.

***

### Key Considerations

> ⚠️ Past Scenarios
>
> When selecting a benchmark, you may see a warning: "The selected scenario is in the past. Recommendations may no longer be relevant." Always ensure your target benchmark is relevant to your current optimization period for the most accurate recommendations.

<Image align="center" alt="Warning message for selecting a past scenario." width="350px" src="https://files.readme.io/48740361a4795da7bbd3e44603d7d79e9554b3979413df05db455300df27aa34-Target_Benchmark_-_Default_Scenario.png" />

<br />

To learn more about how the Attribution Recommendations are made, read the [detailed documentation.]()
