---
title: '[4.0][Updated]Model Calibration: Make the model agree with your experiments'
excerpt: >-
  Feed incrementality evidence into the model so its paid-media estimates match
  what your tests actually proved. evidence during model creation or
  calibration.
deprecated: false
hidden: true
metadata:
  title: 'Model Calibration: Make the model agree with your experiments'
  keywords:
    - Lifesight Model Calibration
  robots: noindex
---
Without calibration, the model works out each channel's contribution by looking at patterns in your historical spend and sales. That works, but it's still an estimate based on correlation.&#x20;

Calibration lets you hand the model something stronger: the result of an actual experiment. If a geo holdout showed Meta drove a specific incremental lift, calibration tells the model to stay close to that number instead of guessing at it.&#x20;

Your channel results are then anchored to something you tested, not just something the data suggested.

## When calibration is useful

Use calibration when a reliable incrementality experiment covers a channel and period represented in the model data. The evidence should use a comparable outcome and a clearly defined experiment window.

## Add calibration evidence

Calibration is configured in the **Calibration** step while creating a model or retraining an existing model.

1. Select **Add calibration**.
2. Choose the paid-media variable.
3. Enter the experiment start and end dates.
4. Enter the incremental ROAS or supported incremental efficiency value.
5. Enter the confidence value.
6. Review the entries before submitting the model.

![](https://files.readme.io/861852fc7a6c15be6605628119867547b77bd88233dd2ee4d511a86708a1734d-Screenshot_2026-09-11_at_11.35.05_AM.png)

Eligible calibration values can also be inherited from the champion model during creation or retraining.

<Callout icon="📘" theme="info">
  ### Experiment results are entered manually. Directly adding an experiment from the experiment picker is not currently available.
</Callout>

## Review calibration

After training, open **Diagnostics** and review the calibration summary. Confirm that the channel, dates, incremental efficiency, and confidence match the evidence used for training.

![](https://files.readme.io/4e1333d8c931fcbd03f6cb62763d7fdaf953cc48c20175252d5342534d8c8155-Screenshot_2026-09-11_at_11.36.07_AM.png)

<br />Calibration should be interpreted with the model's backtesting, uncertainty, causal structure, and contribution results. It strengthens the connection to observed lift, but does not replace model validation.

## Update calibration evidence

To change calibration inputs for an existing model, start a retraining workflow and edit the Calibration step. The existing model's Diagnostics tab is read-only.

**\[VIDEO PLACEHOLDER: Adding calibration during model creation or retraining]**
