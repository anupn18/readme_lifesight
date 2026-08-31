---
title: '[4.0][WIP] Setting up your Mix Model'
excerpt: >-
  Your guide to configuring data, selecting variables, and launching your media
  mix model
deprecated: false
hidden: true
metadata:
  robots: noindex
---
## Data Requirements

To ensure a successful model build, your data must be correctly prepared. You can provide data to the Lifesight platform through two methods:

### Using a Data Model

To create a model using data already available in Lifesight, select an existing Data Model from your workspace. Data Models bring together the fields configured from your connected sources and make them available for variable mapping during model creation.

### Using a CSV File

You can also create a model using historical data stored in a CSV file. The file must meet the required formatting and validation conditions to prevent errors during model creation.

Refer to the [CSV Data Formatting Guidelines](https://docs.lifesight.io/v2.0/docs/4-0-wip-mmm-input-schema) for more details about preparing your CSV file.

## Interactive Demo

> 📘 View a step-by-step walkthrough
>
> Use the interactive demo below to guide you through each step of the model creation process.
>
> **[VIDEO PLACEHOLDER: Creating a Mix Model in Lifesight 4.0]**

<br />

## Step 1: Select the Model Class

**[IMAGE PLACEHOLDER: Create Model screen showing the model name and Model Class options]**

1. Select **Models** from the sidebar.
2. Click the **`Create Model`** button.
3. Enter a unique and descriptive name for your model.
4. Select **Media Mix Model** as the Model Class.
5. Click **`Next`**.

***

## Step 2: Map Variables

In this step, you will select your input data and map its fields to the variables required by the model. This is critical for ensuring the model interprets your data correctly.

**[IMAGE PLACEHOLDER: Variable mapping screen showing the data source and variable sections]**

### Select a Data Source

Choose one of the following options:

* **Data Model**: Select a Data Model that has already been configured in your workspace.
* **CSV Upload**: Drag and drop or browse for your prepared CSV file.

### Map Data Features

* **Outcome KPI**: Select the primary metric you want to measure, such as `revenue`, `orders`, or `new_customers`. This is the model's dependent variable.
* **Paid Marketing Variables**: Add each paid media channel or tactic, then map its spend field. Where available, you can also map impressions and clicks.
* **Organic Variables**: Map non-paid variables such as `SEO_Sessions`, `Direct_Traffic`, or email activity.
* **Contextual Variables**: Map external factors such as `Competitor_Promotions`, pricing changes, or promotional events.
* **Halo Variables**: Add variables that may influence other marketing activity or help explain cross-channel effects.
* **Dimensions**: If your data is dimensional, select the fields that should be used to segment the model.

For organic, contextual, and halo variables, select the expected treatment:

> 📘 What Treatment Should I Choose?
>
> * **Positive**: Select this when the variable is expected to increase your Outcome KPI. Example: Your own brand's promotional event.
> * **Negative**: Select this when the variable is expected to decrease your Outcome KPI. Example: A major competitor's promotional campaign.
> * **Neutral**: Select this when you are unsure or want the model to determine the effect without guidance.

Once the mapping is complete, click **`Proceed Manually`**.

***

## Step 3: Configure Model Settings

Here, you will set the core parameters for your model's analysis.

**[IMAGE PLACEHOLDER: Configuration screen showing model details, date settings, and training split]**

1. **Model Details**: Confirm the model name. The model owner is filled automatically and is read-only.
2. **Aggregation**: Select **Daily**, **Weekly**, or **Monthly** to match the aggregation of your input data.
3. **Date Range**: Confirm the start and end dates for the model's analysis.
4. **Country & Currency**: Select your primary country of operation and reporting currency. Selecting a country helps the model account for national holidays.
5. **Pre-configured Variables**: Enable or disable contextual factors such as **Seasonality**, **Weekdays**, **Holidays**, and **Trend**. We recommend keeping relevant factors enabled to improve model accuracy.
6. **Refresh Frequency**: Choose how often you want the model to be updated with new data.
7. **Training Size**: Select the percentage or range of data to use for training. The remaining data is used for validation to test the model's accuracy.

### Advanced Settings

> 👍 This section allows data scientists and advanced users to fine-tune the model's underlying parameters.

For each paid media tactic, you can review and modify its Adstock and Saturation settings.

**[IMAGE PLACEHOLDER: Advanced Settings showing Adstock and Saturation controls for a tactic]**

* **Adstock**: This accounts for the delayed or carryover effect of advertising. You can choose between two transformation methods:
  * **Geometric**: A simple decay model.
  * **Flexible (Weibull PDF)**: A more versatile method that can model complex decay patterns.
* **Saturation**: This models diminishing returns, where additional spend on a channel stops producing proportional increases in your KPI.
* **Inherit from Model**: Where available, use settings from a previous model as a starting point for the current configuration.

Keep the default advanced settings unless you have a specific modelling reason to change them.

***

## Step 4: Calibrate Your Model

If you have run recent marketing experiments, such as lift studies or geo experiments, you can use their results to calibrate your MMM. Calibration anchors the model's estimates to observed incrementality and can improve the accuracy of its results.

**[IMAGE PLACEHOLDER: Calibration table showing channel, date range, incremental ROAS, confidence, and calibration type]**

To add a calibration insight:

1. Click **`Add calibration`**.
2. Select the paid media channel or tactic associated with the experiment.
3. Specify the experiment's start and end dates.
4. Enter the observed **Incremental ROAS**.
5. Enter the **Confidence** percentage for the experiment result.

Lifesight automatically determines the calibration type based on the experiment dates and the model's training window. Enter experiment evidence manually, or inherit eligible calibration entries from an existing model. Directly adding a result from Experiments is not currently available.

Calibration is optional. If you do not have suitable experiment results, you can continue to the next step without adding an entry.

***

## Step 5: Define Causal Relationships

This step establishes the causal links between your input variables and the Outcome KPI. The relationships you define guide the model in understanding which factors may influence one another and the final result.

**[IMAGE PLACEHOLDER: Causal Relationships table alongside the visual Preview map]**

On this screen, you will see two main sections: the **Relationships** table on the left and a visual **Preview** map on the right.

1. **Review the Relationship Pairs**: Each row represents a possible relationship between a **Cause** variable, such as `facebook_spend`, and an **Effect** variable, such as `Orders`.
2. **Set the Relationship**: Use the toggle to classify each pair:
   * **Potential**: Select this when the Cause variable may influence the Effect variable.
   * **Forbidden**: Select this when the causal relationship should not be considered by the model.
3. **Use the Visual Preview**: The graph updates as you change the relationships. Use it to confirm that the connections and direction of influence make sense.
4. Click **`Next`** when you have reviewed the relationships.

***

## Step 6: Review and Submit Your Model

Review the model summary before submitting it.

**[IMAGE PLACEHOLDER: Final review screen showing the model summary and Submit button]**

Confirm the following details:

* Model name, class, and owner
* Paid, organic, contextual, and halo variables
* Analysis date range and aggregation
* Training size and refresh frequency
* Calibration entries

If any required information is missing, return to the relevant step and complete it. When the model is ready, click **`Submit`** to start the model run.

The model will appear in the Models list with its current processing status. You will be notified when the run has completed successfully.

**[IMAGE PLACEHOLDER: Models list showing a model in progress and a completed model]**

After the model is created, open it to review its performance, contribution insights, response curves, and other available results.