---
title: '[4.0][Updated] Setting up your Marketing Mix Model'
excerpt: >-
  Your guide to configure data, select variables, and launching your marketing
  mix model
deprecated: false
hidden: true
metadata:
  title: 'Setting up your Marketing Mix Model '
  keywords:
    - Lifesight Marketing Mix Model
  robots: noindex
---
Setting up a marketing mix model is mostly about the inputs. Lets see what your data needs to look like, how to choose the variables the model learns from, and what happens once you hit build. Get this part right and everything downstream, from contribution to budget planning, holds up.

## Data Requirements

To ensure a successful model build, your data must be correctly prepared. You can provide data to the Lifesight platform through two methods:

### Using a Data Model

To create a model using data already available in Lifesight, select an existing Data Model from your workspace. Data Models bring together the fields configured from your connected sources and make them available for variable mapping during model creation.

![](https://files.readme.io/db81cefebf8f29d0de261a0097fcbe942a9601897419366175788e1a1fc070a0-Screenshot_2026-09-11_at_3.41.56_PM.png)

### Using a CSV File

You can also create a model using historical data stored in a CSV file. The file must meet the required formatting and validation conditions to prevent errors during model creation.

Refer to the <Anchor target="_blank" href="https://docs.lifesight.io/v2.0/update/docs/mmm-csv-data-formatting">CSV Data Formatting Guidelines</Anchor> for more details about preparing your CSV file.

![](https://files.readme.io/e4931e78d18df9e42200653c9e88a65f8ba02112ccf80c98a6901f5a110e24b3-Screenshot_2026-09-08_at_9.02.28_AM.png)

## Interactive Demo

<Callout icon="📘" theme="info">
  ### View a step-by-step walkthrough

  Use the interactive demo below to guide you through each step of the model creation process.

  **\[VIDEO PLACEHOLDER: Creating a Mix Model in Lifesight 4.0]**
</Callout>

## Step 1: Select the Model Class

1. Select`  Models  `from the sidebar to see every model in your workspace.
2. Click `Create Model` to start a new build.
3. Give your model a unique, descriptive name, so you can tell versions apart later.
4. Select `Marketing Mix Model `as the Model Class, which measures channel contribution to revenue across paid, owned, and earned media.
5. Click Next to move on to variables.

   ![](https://files.readme.io/5a9bc4f88acf9078bceeef82c230cd864a721216d88b86584ecb91fe794522fd-Screenshot_2026-09-08_at_9.04.36_AM.png)

<br />

***

## Step 2: Map Variables

In this step, you will select your input data and map its fields to the variables required by the model. This is critical for ensuring the model interprets your data correctly.

### Select a Data Source

Choose one of the following options:

* **Data Model**: Select a Data Model that has already been configured in your workspace.
* **CSV Upload**: Drag and drop or browse for your prepared CSV file.

![](https://files.readme.io/c247b6cf3c245638ef09d23955ce3debbfe6b675db2a03b724167b22e308b4bf-Screenshot_2026-09-08_at_9.02.01_AM.png)

### Map Data Features

* **Outcome KPI**: Select the primary metric you want to measure, such as `revenue`, `orders`, or `new_customers`. This is the model's dependent variable.
* **Paid Marketing Variables**: Add each paid media channel or tactic, then map its spend field. Where available, you can also map impressions and clicks.
* **Organic Variables**: Map non-paid variables such as `SEO_Sessions`, `Direct_Traffic`, or email activity.
* **Contextual Variables**: Map external factors such as `Competitor_Promotions`, pricing changes, or promotional events.
* **Halo Variables**: Add variables that may influence other marketing activity or help explain cross-channel effects.
* **Dimensions**: If your data is dimensional, select the fields that should be used to segment the model.

For organic, contextual, and halo variables, select the expected treatment:

<Callout icon="📘" theme="info">
  ### What Treatment Should I Choose?

  * **Positive**: Select this when the variable is expected to increase your Outcome KPI. Example: Your own brand's promotional event.
  * **Negative**: Select this when the variable is expected to decrease your Outcome KPI. Example: A major competitor's promotional campaign.
  * **Neutral**: Select this when you are unsure or want the model to determine the effect without guidance.
</Callout>

Once the mapping is complete, click `Proceed Manually`.

***

## Step 3: Configure Model Settings

Here, you will set the core parameters for your model's analysis.

![](https://files.readme.io/8787aa223e5742ea6d2424b43df9855ea26baad420ba626e3340b86056f43cab-Screenshot_2026-09-08_at_9.05.09_AM.png)

1. **Model Details**: Confirm the model name. The model owner is filled automatically and is read-only.
2. **Aggregation**: Select **Daily**, **Weekly**, or **Monthly** to match the aggregation of your input data.
3. **Date Range**: Confirm the start and end dates for the model's analysis.
4. **Country & Currency**: Select your primary country of operation and reporting currency. Selecting a country helps the model account for national holidays.
5. **Pre-configured Variables**: Enable or disable contextual factors such as **Seasonality**, **Weekdays**, **Holidays**, and **Trend**. We recommend keeping relevant factors enabled to improve model accuracy.
6. **Refresh Frequency**: Choose how often you want the model to be updated with new data.
7. **Training Size**: Select the percentage or range of data to use for training. The remaining data is used for validation to test the model's accuracy.

### Advanced Settings

<Callout icon="👍" theme="okay">
  ### This section allows data scientists and advanced users to fine-tune the model's underlying parameters.
</Callout>

For each paid media tactic, you can review and modify its Adstock and Saturation settings.

![](https://files.readme.io/bbcdc92b8a413566b86b07fce43f1c9654b34e577ec1eaab3cfa6076f506cd55-Screenshot_2026-09-08_at_9.05.55_AM.png)

* **Adstock**: This accounts for the delayed or carryover effect of advertising. You can choose between two transformation methods:
  * **Geometric**: A simple decay model.
  * **Flexible (Weibull PDF)**: A more versatile method that can model complex decay patterns.
* **Saturation**: This models diminishing returns, where additional spend on a channel stops producing proportional increases in your KPI.
* **Inherit from Model**: Where available, use settings from a previous model as a starting point for the current configuration.

Keep the default advanced settings unless you have a specific modelling reason to change them.

***

## Step 4: Calibrate Your Model

If you have run recent marketing experiments, such as lift studies or geo experiments, you can use their results to calibrate your MMM. Calibration anchors the model's estimates to observed incrementality and can improve the accuracy of its results.

![](https://files.readme.io/71db8360aa4b28764071b39e2d3f3bfe8b5e8fea025ceeb9c6363c09d1ea43ae-Screenshot_2026-09-08_at_9.07.39_AM.png)

To add a calibration insight:

1. Click `Add calibration`.
2. Select the paid media channel or tactic associated with the experiment.
3. Specify the experiment's start and end dates.
4. Enter the observed **Incremental ROAS**.
5. Enter the **Confidence** percentage for the experiment result.

Lifesight automatically determines the calibration type based on the experiment dates and the model's training window. Enter experiment evidence manually, or inherit eligible calibration entries from an existing model. Directly adding a result from Experiments is not currently available.

Calibration is optional. If you do not have suitable experiment results, you can continue to the next step without adding an entry.

***

## Step 5: Define Causal Relationships

This step establishes the causal links between your input variables and the Outcome KPI. The relationships you define guide the model in understanding which factors may influence one another and the final result.

![](https://files.readme.io/b357d4f3e65c43af3b88f239dc73f9993e8427b959a6a8c8c05f2698bcf17eec-Screenshot_2026-09-08_at_9.07.58_AM.png)

On this screen, you will see two main sections: the **Relationships** table on the left and a visual **Preview** map on the right.

1. **Review the Relationship Pairs**: Each row represents a possible relationship between a **Cause** variable, such as `facebook_spend`, and an **Effect** variable, such as `Orders`.
2. **Set the Relationship**: Use the toggle to classify each pair:
   * **Potential**: Select this when the Cause variable may influence the Effect variable.
   * **Forbidden**: Select this when the causal relationship should not be considered by the model.
3. **Use the Visual Preview**: The graph updates as you change the relationships. Use it to confirm that the connections and direction of influence make sense.
4. Click `Next` when you have reviewed the relationships.

***

## Step 6: Review and Submit Your Model

Review the model summary before submitting it.

![](https://files.readme.io/0167029d29b80ab13ac69d96ae9c0b092929000ff23a7a72d785a297675cbfec-Screenshot_2026-09-08_at_9.08.40_AM.png)

Confirm the following details:

* Model name, class, and owner
* Paid, organic, contextual, and halo variables
* Analysis date range and aggregation
* Training size and refresh frequency
* Calibration entries

If any required information is missing, return to the relevant step and complete it. When the model is ready, click `Submit` to start the model run.

The model will appear in the Models list with its current processing status. You will be notified when the run has completed successfully.

![](https://files.readme.io/d094c34b32e572d63794f9ee579609a4e42f1b9305d689312dbbe587ee4f34d9-Screenshot_2026-09-08_at_9.09.37_AM.png)

After the model is created, open it to review its performance, contribution insights, response curves, and other available results.
