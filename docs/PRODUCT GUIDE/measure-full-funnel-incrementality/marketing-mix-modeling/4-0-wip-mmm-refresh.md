---
title: '[4.0][WIP] Model Refresh'
excerpt: Refresh a successful model with newly available observations.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
A model refresh incorporates new data while retaining the current model structure and fitted assumptions. Use refresh to keep a successful model current without starting a full retraining workflow.

## When to Refresh

Refresh a model when:

* New periods of data are available.
* The underlying variable structure remains valid.
* Channel definitions and business outcomes have not materially changed.
* You want to compare recent contribution with the prior model window.

Use retraining instead when variables, causal assumptions, hyperparameters, or market relationships require a deeper rebuild.

## Run a Refresh

1. Navigate to **Measure > Models**.
2. Select an eligible model with **Success** or **Refresh Success** status.
3. Open the **Refresh** tab.
4. Click **`Run refresh`**.
5. Upload the CSV containing the updated model data.
6. Review the detected data window and submit the refresh.

**[IMAGE PLACEHOLDER: New Refresh dialog showing CSV upload and date window]**

The Refresh tab appears after a refresh has run. Access also depends on model status and workspace permissions.

## Refresh History

The history view records refresh runs and their status. Expand a run to review its window and available comparison details.

Refresh results can include:

* Model and comparison date ranges
* Metric changes
* Variable additions or removals
* Category-level contribution changes
* Accuracy or MAPE movement
* Partial or failed refresh information

**[IMAGE PLACEHOLDER: Refresh history with one completed run expanded]**

## Review Refresh Impact

Open the related Contribution comparison to review the refreshed period against its comparison period. Pay attention to:

* Changes in spend and incremental outcome
* Efficiency movement
* Contribution shifts by channel and tactic
* New, removed, or unmatched variables
* Unknown contribution after a partial refresh

> 📘 A partial refresh can leave some contribution unattributed. Lifesight displays this in the Unknown group so it is not silently assigned to another channel.

## Refresh Status

* **Refresh In Progress:** The new data is being processed.
* **Refresh Success:** The refresh completed and updated results are available.
* **Partial Refresh:** Some results were updated, but one or more variables could not be attributed completely.
* **Refresh Failed:** The refresh did not complete. Review the error and input data before retrying.

## Best Practices

* Use the same schema and aggregation as the original model.
* Include a continuous date range with no unintended gaps.
* Investigate large metric or contribution changes.
* Run a full retraining when the model structure no longer reflects the business.

**[VIDEO PLACEHOLDER: Running and reviewing a model refresh in Lifesight 4.0]**
