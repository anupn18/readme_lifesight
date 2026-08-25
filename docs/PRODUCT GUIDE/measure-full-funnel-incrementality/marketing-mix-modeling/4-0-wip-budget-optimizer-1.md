---
title: '[4.0][WIP] MMM Budget Optimizer'
excerpt: Use Planner scenarios to evaluate and optimize marketing budgets.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
In Lifesight 4.0, MMM budget optimization is available through **Planner**. Planner uses a successful Marketing Mix Model to simulate budget scenarios, apply constraints, and forecast the expected outcome.

## Before You Begin

Confirm that:

* The selected model has completed successfully.
* The model's diagnostics and causal evidence are suitable for planning.
* The model includes current spend and fitted response curves for the channels you want to optimize.
* Cost settings are configured if you plan against profit.

> 📘 Refresh or retrain an outdated model before using it for a high-impact planning decision.

## Create a Plan

1. Navigate to **Plan > Planner** and click **`New Plan`**.
2. Select the base Marketing Mix Model.
3. Choose the outcome and planning goal supported by the model.
4. Enter the forecast period and the historical basis period.
5. Enter the total budget or target required by the selected goal.
6. Review channel constraints and advanced settings.
7. Run the scenario.

You can also start a plan from an eligible model by clicking **`Create a Plan`** in the model workspace.

**[IMAGE PLACEHOLDER: New Plan wizard with model, goal, forecast period, and budget settings]**

## Current and Optimized Budget

Planner compares the current allocation with the optimized allocation for each channel.

* **Current Budget:** The spend observed in the basis period, scaled to the planning horizon where applicable.
* **Optimized Budget:** The allocation recommended by the scenario under the selected goal and constraints.
* **Current Outcome:** The modelled response for the current allocation.
* **Optimized Outcome:** The forecast response for the optimized allocation.
* **Efficiency:** iROAS for revenue or profit outcomes, and iCPA for unit outcomes such as orders or conversions.

## Constraints

Constraints define how much each channel can move from its current allocation. Use the available presets as a starting point, then adjust channel-level bounds where business requirements demand it.

Advanced controls can be used for more specific pacing and allocation requirements. Avoid setting bounds so tightly that the optimizer has no meaningful room to reallocate budget.

**[IMAGE PLACEHOLDER: Channel allocation table showing current budget, optimized budget, and bounds]**

## Saturation and Marginal Response

The optimizer uses fitted response curves to estimate how additional or reduced spend changes the outcome. A channel close to saturation may have limited value from incremental budget, while a channel with strong marginal response may support additional investment.

Response curves are model estimates. Review them with confidence intervals, causal evidence, recent business changes, and operational constraints.

## Compare Scenarios

Create additional scenarios to test different budgets or constraint strategies. Each scenario must be run before its results can be compared.

Use the scenario workspace to compare:

* Budget allocation
* Forecast outcome
* Incremental response
* Efficiency
* Channel recommendations

When a scenario is ready for action, eligible users can promote it to a decision.

**[VIDEO PLACEHOLDER: Creating and comparing MMM budget scenarios in Planner]**

## Recommendations

* Treat the optimized allocation as a decision input, not an automatic media-buy instruction.
* Investigate large allocation shifts before approval.
* Review channels with weak causal evidence or broad confidence intervals.
* Re-run scenarios when the total budget, forecast period, or constraints change.
* Track the promoted decision and compare results with the model forecast.
