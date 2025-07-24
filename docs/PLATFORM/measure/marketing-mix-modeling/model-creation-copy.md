---
title: Model creation (COPY)
excerpt: Create your first MMM model in minutes and get incremental insights
deprecated: false
hidden: true
metadata:
  robots: index
next:
  pages:
    - slug: overview
      title: MMM Overview
      type: basic
---
Before You Begin: Data Requirements\
To ensure a successful model build, your data must be correctly prepared. You can provide data to the Lifesight platform through two methods:

Using Integrated Data\
For a more automated workflow, you can connect your data sources directly to the platform. To do this, you must first set up the Google Sheets MMM data integration from the Integrations section in the Lifesight dashboard. Once your integration is active, choose Using Integrated data in the upload section to automatically pull all your input data from the connected sheet.

[https://files.readme.io/4763a9b700e3f2e1db2a3a0494db28cb23a5a38a3312203440ca47a9bce5c528-integrations.jpg](https://files.readme.io/4763a9b700e3f2e1db2a3a0494db28cb23a5a38a3312203440ca47a9bce5c528-integrations.jpg)" width="700" alt="Integrations Screen"/>

Using a CSV File\
If you are uploading a CSV file, it must meet the following conditions to prevent errors during the model creation process.

🚧 CSV Formatting Rules

* The file must include a

Date column in yyyy-mm-dd format. Data can be aggregated daily, weekly, or monthly, but there should be no missing dates in the sequence.

* All marketing variables (spends, impressions, clicks) and contextual variables must be numeric.

* There should be no empty or null values. Replace any nulls with

0. <br />

* No marketing variable column should have a sum of zero. If a column's total is zero, please remove it from the dataset before uploading.

* Column headers must only contain alphanumeric characters and underscores (e.g.,

Facebook\_Spend, not Facebook Spend).

* All column headers must begin with an alphabet character.

Interactive Demo\
📘 View a step-by-step walkthrough

Want to see it in action? Use the interactive demo below to guide you through each step of the model creation process.

\[Placeholder for Interactive Demo]

Step 1: Initiate Model Creation and Upload Data\
Navigate to the MMM module by selecting Measure > Models.

Click the Create Model button.

Enter a unique and descriptive name for your model in the top-left section.

In the upload section, choose your data source:

Select Using Integrated data if you have configured the Google Sheets integration.

Select Upload a file to drag-and-drop or browse for your prepared CSV file.

Click Next.

Step 2: Map Features (Schema Mapping)\
In this step, you will associate the columns from your dataset with Lifesight's required data types. This is critical for ensuring the model interprets your data correctly.

Outcome KPI: Select the primary metric you want to measure, such as revenue, orders, or new\_customers. This is your model's dependent variable.

Paid Marketing Spend: Map the spend or cost columns for each paid media channel (e.g., Facebook\_Spend, Google Search\_Spend) to its corresponding Platform.

Paid Marketing Clicks: Map the clicks columns for each channel to its Platform.

Paid Marketing Impressions: Map the impressions columns for each channel to its Platform.

Organic Variables: For non-paid channels like SEO\_Sessions or Direct\_Traffic, map the variable and define its expected Impact (Positive, Negative, or Neutral) on your outcome KPI.

Contextual Variables: For external factors like Competitor\_Promotions or Holiday\_Sales, map the variable and define its Impact.

📘 What Impact Should I Choose?

Positive: Select this if the variable is expected to increase your Outcome KPI. Example: Your own brand's promotional events.

Negative: Select this if the variable is expected to decrease your Outcome KPI. Example: A major competitor's promotional campaign.

Neutral: Select this if you are unsure or want the model to determine the effect without guidance.

Step 3: Configure Model Settings\
Here, you will set the core parameters for your model's analysis.

Aggregation: Select Daily, Weekly, or Monthly to match the aggregation of your input data.

Date Range: Confirm the start and end dates for the model's analysis.

Pre-configured Variables: Enable or disable contextual factors like Seasonality, Weekdays, Holidays, and Trends. It is highly recommended to keep these enabled to improve model accuracy.

Country & Currency: Select your primary country of operation and reporting currency. Selecting a country helps the model automatically account for national holidays.

Refresh Frequency: Choose how often you want your model to be updated with new data.

Training Size: Specify the percentage of data to be used for training (e.g., 85%). The remaining data will be used for validation to test the model's accuracy.

Step 4: (Optional) Apply Advanced Settings & Calibration\
This section allows data scientists and advanced users to fine-tune the model's underlying parameters.

Adstock and Saturation\
For each marketing channel, you can modify its Adstock and Saturation settings.

Adstock: This accounts for the delayed or carryover effect of advertising. You can choose between two transformation methods:

Geometric: A simple decay model.

Flexible (Weibull PDF): A more versatile method that can model more complex decay patterns. We recommend using Flexible.

Saturation: This models the point of diminishing returns, where additional spend on a channel stops yielding proportional increases in your KPI.

Calibrate Your Model\
If you have run marketing experiments (e.g., lift studies, geo-tests), you can use the results to calibrate your MMM. This process anchors the model's results to real-world observations, significantly improving its accuracy.

To add a calibration insight:

Click Add Calibration.

Select the Platform (channel) the experiment was run on.

Specify the Start and End Date of the experiment.

Enter the total Spend for that period.

Input the observed Incremental lift and the Confidence Level of your experiment's result.

Step 5: Create and Run Your Model\
Once you have reviewed your configuration:

Click the Create Model button at the bottom of the page.

The model's status will change to "In progress". You will be notified once the model has run successfully and the status changes to "Success".

After your model is created, you can navigate to the MMM Overview tab to uncover insights and analyze your results.