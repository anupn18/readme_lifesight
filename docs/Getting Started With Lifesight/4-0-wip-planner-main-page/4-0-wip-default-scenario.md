---
title: '[4.0][WIP] Default Scenario'
excerpt: Lifesight 4.0 WIP guide for Default Scenario.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Default Scenario

In Lifesight 4.0, the scenario promoted to Decisions acts as the workspace's default scenario. Its plan is loaded on the Planner home view and supplies recommendations to supported downstream workflows.

[IMAGE PLACEHOLDER: Promoted scenario indicator in Planner]

## Promote a scenario

1. Open a saved plan from **Plan List**.
2. Select the scenario you want to use.
3. Review its configuration and completed results.
4. Select **Promote to Decision**.
5. Confirm the promotion.

[VIDEO PLACEHOLDER: Promoting a Planner scenario]

The promoted scenario is marked in the plan and Plan List. Promoting another scenario replaces the active promoted selection for the workspace.

## Default Planner view

The promoted plan is shown when you open Planner without selecting another plan. This passive home view is read-only. Open the plan from Plan List to edit it, rerun scenarios, or make a new scenario.

## Change or remove the default

Promote a different completed scenario to change the default. Use **Demote** in Plan List to remove the current promotion without deleting the plan.

[IMAGE PLACEHOLDER: Demote action in Plan List]

## Downstream use

The promoted scenario can power Attribution pacing and recommendations and can be opened in Deploy for implementation.

> Promote only after reviewing model choice, dates, budget, constraints, forecast, and channel recommendations.
