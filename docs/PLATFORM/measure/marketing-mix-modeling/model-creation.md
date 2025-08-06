---
title: Model Creation
excerpt: >-
  Your guide to configuring data, selecting variables, and launching your media
  mix model
deprecated: false
hidden: false
metadata:
  robots: index
---
## Data Requirements

To ensure a successful model build, your data must be correctly prepared. You can provide data to the Lifesight platform through two methods:

### Using Integrated Data

To create a model with an automated workflow, you can connect your data sources directly to the platform. To do this, you  connectors from the [integrations](https://docs.lifesight.io/update/docs/native-integrations#/) section in the Lifesight platform. Once your integration is active, choose **Using Integrated data** in the upload section to automatically pull all your input data from integrated platforms.

### Using a CSV File

While the recommended method to create a model is using Integrated data, you can also kickstart your model with historical data stored in a CSV file. To ensure the model is built successfully, it must meet the certain conditions to prevent errors during the model creation process.

Refer to this [page](https://docs.lifesight.io/update/docs/mmm-input-schema#/) for a more details on data requirements for CSV file input.

<br />

## Interactive Demo

> 📘 View a step-by-step walkthrough
>
> Use the interactive demo below to guide you through each step of the model creation process
>
> <HTMLBlock>{`
> <div>
>   <script async src="https://js.storylane.io/js/v2/storylane.js"></script>
>   <div class="sl-embed" style="position:relative;padding-bottom:calc(48.63% + 25px);width:100%;height:0;transform:scale(1)">
>     <iframe loading="lazy" class="sl-demo" src="https://lifesight.storylane.io/demo/2ckzf7dpatbk?embed=inline" name="sl-embed" allow="fullscreen" allowfullscreen style="position:absolute;top:0;left:0;width:100%!important;height:100%!important;border:1px solid rgba(63,95,172,0.35);box-shadow: 0px 0px 18px rgba(26, 19, 72, 0.15);border-radius:10px;box-sizing:border-box;"></iframe>
>   </div>
> </div>
> `}</HTMLBlock>
>
>

<br />

## Step 1: Initiate Model Creation and Upload Data

<Image align="center" src="https://files.readme.io/e9b7983f812e124204572cd480162309f5c4ef0e5fa5ed2555a13446e02bb5e1-Model_creation_-_data_sources_page.png" />

1. Navigate to the MMM page by selecting **Measure > Models**.
2. Click the **`Create Model`** button.
3. Enter a unique and descriptive name for your model in the top-left section.
4. In the upload section, choose your data source:
   * Select **Using Integrated data** if you have configured the Google Sheets integration.
   * Select **Upload a file** to drag-and-drop or browse for your prepared CSV file.
5. Click **`Next`**.

***

## Step 2: Map Features (Schema Mapping)

In this step, you will associate the columns from your dataset with Lifesight's required data fields. This is critical for ensuring the model interprets your data correctly.

<Image align="center" src="https://files.readme.io/f72266d482a5328f29280cbcec3c629a6016ef9c4b09be5bc212874b5c881e4f-Model_creation_-_Feature_selection_page.png" />

* **Outcome KPI**: Select the primary metric you want to measure, such as `revenue`, `orders`, or `new_customers`. This is your model's dependent variable.
* **Paid Marketing Variables**: Map the spend, impressions, clicks, fields from the input data source to the channel/tactic names for each paid media channel. (e.g., `Facebook_Spend`, `Google Search_Spend`)
* **Organic Variables**: For non-paid channels like `SEO_Sessions` or `Direct_Traffic`, map the variable and define its expected **Impact** (Positive, Negative, or Neutral) on your outcome KPI.
* **Contextual Variables**: For external factors like `Competitor_Promotions` or `Holiday_Sales`, map the variable and define its **Impact**.

> 📘 What Impact Should I Choose?
>
> * **Positive**: Select this if the variable is expected to increase your Outcome KPI. Example: Your own brand's promotional events.
> * **Negative**: Select this if the variable is expected to decrease your Outcome KPI. Example: A major competitor's promotional campaign.
> * **Neutral**: Select this if you are unsure or want the model to determine the effect without guidance.

***

## Step 3: Configure Model Settings

Here, you will set the core parameters for your model's analysis.

<Image align="center" src="https://files.readme.io/1906821f2aa1362a67ba194e344637ae82f0e4a4218bef183c27dc722c3c17cf-ScreenShot_Tool_-20250724194716.png" />

1. **Aggregation**: Select **Daily**, **Weekly**, or **Monthly** to match the aggregation of your input data.
2. **Date Range**: Confirm the start and end dates for the model's analysis.
3. **Pre-configured Variables**: Enable or disable contextual factors like **Seasonality**, **Weekdays**, **Holidays**, and **Trends**. It is highly recommended to keep these enabled to improve model accuracy.
4. **Country & Currency**: Select your primary country of operation and reporting currency. Selecting a country helps the model automatically account for national holidays.
5. **Refresh Frequency**: Choose how often you want your model to be updated with new data.
6. **Training Size**: Specify the fraction of data to be used for training (e.g., 0.85 for utilizing 85% of the entire input data set). The remaining data will be used for validation to test the model's accuracy.

***

## Step 4: Apply Advanced Settings

> 👍 This section allows data scientists and advanced users to fine-tune the model's underlying parameters.

### Adstock and Saturation

For each marketing channel, you can modify its **Adstock** and **Saturation** settings.

<Image align="center" src="https://files.readme.io/f15e689bb2ec794de42fa8c4862c790bf813b936127f75422ff638992d607c06-ScreenShot_Tool_-20250724195223.png" />

* **Adstock**: This accounts for the delayed or carryover effect of advertising. You can choose between two transformation methods:
  * **Geometric**: A simple decay model.
  * **Flexible (Weibull PDF)**: A more versatile method that can model more complex decay patterns. We recommend using **Flexible**.
* **Saturation**: This models the point of diminishing returns, where additional spend on a channel stops yielding proportional increases in your KPI.

## Step 5: Define Relationships

This step is for establishing the causal links between all your input variables (causes) and your outcome KPI (effect). The relationships you define here guide the model in understanding how different factors influence each other and the final result.

<Image align="center" src="https://files.readme.io/9e399d6d44de9d561d3f6751db57e6bd2339fdb71567025d0d64e13a31280d79-ScreenShot_Tool_-20250724195645.png" />

On this screen, you will see two main sections: the **Relationships** table on the left and a visual **Preview** map on the right.

1. **Review the Relationship Pairs**: In the table on the left, review each row, which represents a potential relationship between a **Cause** variable (like `facebook_spend`) and an **Effect** variable (like `Orders`).

2. **Select a Relationship Type**: For each pair, choose one of the three relationship types from the dropdown menu:
   * **Potential (Direct)**: Select this if you believe the **Cause** variable directly influences the **Effect** variable. For example, the relationship between `Direct` traffic and `Orders` is set as a direct one.
   * **Potential (Indirect)**: Select this if the **Cause** is likely to influence the **Effect** through an intermediate variable.
   * **Forbidden**: This is the default for most pairs and indicates that there is no direct causal link between the two variables. For example, `Direct` traffic does not cause `facebook_spend`, so their relationship is forbidden.

3. **Use the Visual Preview**: The graph on the right provides a real-time visualization of the relationships you are defining. Use this map to confirm that the connections and pathways make logical sense. The nodes are color-coded, and the arrows show the direction of influence.

4. **Proceed to the Next Step**: Once you have reviewed and adjusted all the relationships to your satisfaction, click **`Next`** to proceed to the **Calibration** step.

## Step 6: Calibrate Your Model

If you have run any recent marketing experiments (e.g., lift studies, geo-tests), you can use the results to calibrate your MMM. This process anchors the model's results to real-world observations, significantly improving its accuracy.

<Image align="center" src="https://files.readme.io/0052b0bedd9037e51b89b79f1984711d8b0c10f828d961c6bc26039fcdfe4f7a-ScreenShot_Tool_-20250724201607.png" />

To add a calibration insight:

1. Click **Add Calibration**
2. Select the **channel**  the experiment was run on.
3. Specify the **Start and End Date** of the experiment.
4. Enter the total **Spend** for that period.
5. Input the observed **Incremental** lift and the **Confidence Level** of your experiment's result.

***

## Step 7: Create and Run Your Model

Once you have reviewed your configuration:

1. Click the **`Create Model`** button at the bottom of the page.
2. The model's status will change to **"In progress"**. You will be notified once the model has run successfully and the status changes to **"Success"**.

After your model is created, you can navigate to the **MMM Overview** tab to uncover insights and analyze your results.