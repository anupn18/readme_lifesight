---
title: Causal Settings
excerpt: >-
  Set foundational models and configure experiments to inform Causal Attribution
  insights 
deprecated: false
hidden: true
metadata:
  robots: index
---
The **Causal Settings** page is the central hub for configuring the foundational inputs that power Lifesight's Causal Attribution analysis. By specifying your primary conversion methodology, incorporating Marketing Mix Models (MMM), and inputting experiment results, you can refine the accuracy of your attribution insights.

### Configuring Causal Inputs

This section provides a detailed walkthrough of the components available on the Causal Settings page.

#### Selecting an Anchor Attribution Methodology

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/515ea0ddcfa730eef517b5e468d02a6a3c56c279ba9b46a276c9ca32c3c5f96f-Causal_Settings_-_Anchor_Attribution_methodology.png" />

The **Anchor Attribution Methodology** is the primary conversion dataset that the causal engine uses as its source of truth. You can select your preferred methodology from the dropdown menu at the top of the page.

* **PLATFORM Conversions**: This option uses performance metrics (e.g., ROAS, CPA, CPM) reported directly by the ad platforms as the basis for incrementality calculations.
* **GA4 Conversions**: This option utilizes the attribution computations performed by the default algorithm set within your connected Google Analytics 4 workspace.

<br />

#### Marketing Mix Models (MMM)

This section lists the Marketing Mix Models that have a **Default Scenario linked to an output KPI**. Only these designated models are used as inputs for the causal analysis. The default scenario can be set by **starring a scenario within a plan on the Planner page**.

The table provides a summary of each available model:

| Column                | Description                                                                                                                            |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| **Model Name**        | The unique name assigned to the Marketing Mix Model.                                                                                   |
| **Status**            | The current processing state of the model (e.g., `Success`).                                                                           |
| **Input Type**        | How the data for the model was provided (e.g., `upload`, `integrated`).                                                                |
| **Outcome/KPI**       | The primary Key Performance Indicator the model was built to measure (e.g., `Revenue`, `Orders`).                                      |
| **R²**                | A statistical measure that indicates how well the model explains the variance in the KPI. A higher value signifies a better fit.       |
| **NRMSE Value**       | The Normalized Root Mean Square Error, which indicates the model's prediction accuracy. A lower value signifies a more accurate model. |
| **Created On**        | The date the model was initially created.                                                                                              |
| **Last Refreshed On** | The date the model was last updated with new data.                                                                                     |

<br />

To learn how to set a default scenario, check out our guide on [default scenario](https://docs.lifesight.io/update/docs/default-scenario#/)

<br />

#### Managing Experiments

Incorporating the results from controlled experiments is crucial for validating and refining attribution insights. This section allows you to view and add experiment data.

##### **Platform Experiments**

This table displays a list of experiments that have been configured and run directly within the Lifesight Platform.

##### **Adding External Experiments**

You can add the results of experiments conducted on external platforms (e.g., Google Ads, Meta, Outbrain) to include their findings in the causal analysis.

1. Click the **+ Add External Experiments** button.
2. Fill in the details of your experiment in the form that appears.
3. Click **Confirm** to save the experiment.

<br />

<Image align="center" width="650px" src="https://files.readme.io/aa8b4f3fcc77d3640cdd4c14499e40ce98f4f4e543250dee97122c1c8bf19291-Causal_Settings_-_External_Experiments.png" />

<br />

> Fields marked with an asterisk (`*`) are mandatory and must be filled in to proceed.

<br />

The table below provides a detailed description of each field in the **External Experiments** form:

| Field                                         | Description                                                                                     |
| --------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Experiment Name** *                         | A descriptive name for your experiment (e.g., "Outbrain Q3 Campaign Launch").                   |
| **Experiment Platform** *                     | The platform where the experiment was conducted (e.g., `Outbrain`, `Meta`, `Google Ads`).       |
| **Tactic**                                    | The specific marketing tactic that was tested (e.g., "Retargeting," "Prospecting").             |
| **Start Date** *                              | The date the experiment began.                                                                  |
| **End Date** *                                | The date the experiment concluded.                                                              |
| **KPI** *                                     | The primary Key Performance Indicator that was measured (e.g., `Revenue`, `Conversions`).       |
| **Lift %** *                                  | The percentage lift observed in the treatment group compared to the control group.              |
| **iRevenue/iConversions (Treatment Group)** * | The incremental revenue or conversions generated by the group exposed to the test variable.     |
| **iRevenue/iConversions (Control Group)** *   | The incremental revenue or conversions generated by the group not exposed to the test variable. |
| **Spend (Treatment group)** *                 | The total ad spend allocated to the treatment group during the experiment.                      |
| **Spend (Control group)** *                   | The total ad spend allocated to the control group during the experiment.                        |
| **Confidence**                                | The statistical confidence level of the experiment's result (e.g., `90%`, `95%`).               |

<br />

### Impact on Causal Attribution

Once configured, the selections made on this page—your anchor methodology, default MMM outputs, and experiment results—are directly fed into the Lifesight causal engine. This unified approach ensures that your attribution reports are not just correlational, but are calibrated against robust models and real-world test outcomes, providing a more accurate and defensible view of marketing performance.
