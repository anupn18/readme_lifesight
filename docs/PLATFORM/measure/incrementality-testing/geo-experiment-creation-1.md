---
title: Geo Experiment Creation
excerpt: Design and Deploy your Geo Experiment
deprecated: false
hidden: false
metadata:
  robots: index
---
Lifesight's platform allows you to design and deploy geo experiments to accurately measure the incremental impact of your marketing efforts across various ad platforms. This guide walks you through the step-by-step process of designing a new geo experiment.

<br />

## **Interactive Demo: Designing a Geo Experiment**

<Embed typeOfEmbed="iframe" url="https://lifesight.storylane.io/demo/uwyisucnnpa9?embed=inline" html="false" iframe="true" href="https://lifesight.storylane.io/demo/uwyisucnnpa9?embed=inline" height="600px" width="800px" />

<br />

### Initiating a New Experiment

To begin designing your geo experiment, navigate to the **Experiments** section from the main Lifesight UMM dashboard and click on **+ Create Experiment**. You will then be guided through a series of steps: Design, Data, Markets, Campaigns, and Review.

### Step 1: Hypothesis Creation

<Image align="center" src="https://files.readme.io/17e3b5e485a4d58ba4bede04e9c5bcacea085ad8c6aae8e0359c4e3baec82647-Experiment_design_page_-_pre-hypothesis.png" />

The first step in designing your experiment is to define your hypothesis and the type of experiment you wish to run.

#### Experiment Type

Lifesight supports various experiment types. For geo experiments, you will typically select:

* **Geographic**: Assess lift by varying spend across geographical locations.

<br />

#### Defining Your Hypothesis

Within "Cell 1" (and subsequent cells if you are running a multi-cell experiment), you will create your hypothesis.

<Image align="center" src="https://files.readme.io/437ed63d871f0ec22014fe2c8a4a3c1addd0addb3c13f742dbdde026c0907842-Experiment_-_hypothesis_creation_page.png" />

To create your hypothesis:

1. Click on **Create Hypothesis** in the "Cell 1" section.
2. **Hypothesis**: Select the type of incrementality test you want to perform (e.g., "Test Incrementality of Existing Channel").
3. **Channel / Tactic**: Choose the specific channel or tactic you are testing (e.g., Facebook, Google).
4. **Expected CPIC** (Expected Cost Per Incremental Customer): Enter your expected value for the chosen metric.
5. **Expected Lift (%)**: Input the anticipated percentage lift you expect from the experiment.
6. **Significance Level (%)**: Define the desired statistical significance level for your experiment results.
7. **Treatment Type**: Select either **Scale-up** or **Hold-out**.
8. Click **Confirm** to save your hypothesis.

You can add multiple cells to test different hypotheses simultaneously by clicking **+ Add Cell**.

### Step 2: Data Selection and Validation

After defining your hypothesis, you need to select and validate the data that will be used for your experiment. This data helps in analyzing your treatment and control groups.

#### Experiment Duration & Historical Timeframe

* **Experiment Duration**: Select the planned duration for your experiment.
* **Historical Timeframe**: Choose the historical period for data analysis

#### Data Upload

Lifesight provides flexibility in how you bring your data into the platform:

<Image align="center" src="https://files.readme.io/249d5219534169fd7743f247a85b9de3c44e98b5962903cd850a2633cfccb2dc-Experiment_data_page.png" />

* **Upload CSV**: You can upload a CSV file containing your historical data. Historical data for experiment design typically needs to contain 3 fields: Date, Geography (State, City, or Zip Code), and output KPI (Eg: Revenue, Orders, Installs, etc.,)
* **Integrated**: Connect directly to integrated data sources.
* **Google Sheet**: Link a Google Sheet for data ingestion.

#### KPI Selection

Select the Key Performance Indicator (KPI) that your experiment will measure (e.g., Revenue).

#### Region and Geographic Granularity

* **Geographic Granularity**: Define the level of geographic detail for your experiment (e.g., State).
* **Number of Desired Test Markets**: Specify how many test markets you wish to include.

#### Data Validation

After selecting your data parameters, click **Validate**. The system will process your data and confirm its suitability for the experiment. A "Validation Successful" message will appear, confirming details like Geographic Granularity, Date Column, Geo Column, Historical Start Date, Historical End Date, and KPI Column.

<Image align="center" src="https://files.readme.io/9067f54586499343f0596772f384ab960bb151a0e8948df8495951bd31d1ea43-Experiment_-_data_validation_successful_page.png" />

### Step 3: Market Selection

Once your data is validated, you will proceed to select your test and control markets. Lifesight helps you identify optimal market sets based on your historical data.

#### Understanding Test and Control Markets

In a geo experiment, **Test Markets** are the locations where the experiment's treatment (e.g., new campaign, increased spend) is applied. **Control Markets** are similar locations where the treatment is *not* applied, serving as a baseline for comparison.

#### Automatic Market Selection

Based on your historical data, Lifesight's platform will propose the best-suited test market sets for your experiment.

<Image align="center" src="https://files.readme.io/946abe09d4d819e01c10300fa5e6c994bc5382b098ec7df09ad5574dc085fc7f-Experiments_Markets_Selection_page.png" />

#### Reviewing Market Cohorts

You can review the suggested market cohorts for each cell of your hypothesis. Details provided include:

* **Test Markets**: The specific geographic locations designated as test markets (e.g., Arkansas, South Carolina).
* **Duration**: The recommended duration for the experiment in these markets.
* **Market Share**: The percentage of market share represented by these markets.
* **Additional Spend**: The estimated additional spend for the experiment in these markets.
* **Minimum Detectable Lift**: The smallest percentage lift that the experiment is capable of detecting.
* **Estimated Lift**: The projected lift from the experiment.
* **Synthetic Control Imbalance**: A metric indicating the balance between test and synthetic control markets.
* **Estimated Bias**: An estimation of potential bias in the market selection\[cite: 4].
* **Control Markets**: A breakdown of the geographic locations forming the synthetic control group and their respective weights.

You can view the **Time Series Decomposition chart**, below the market selection table to observe historical data trends for both control and treatment groups, which helps ensure the validity of your market selection.

### Step 4: Campaign Deployment

This step involves linking your Lifesight experiment to active campaigns on integrated ad platforms. Currently, Lifesight supports campaign deployment for **Google** and **Meta** ad platforms.

#### Integrating with Ad Platforms

Ensure your Google and Meta ad accounts are integrated with Lifesight. This allows the platform to adjust and monitor campaigns based on your experiment design.

#### Mapping Campaigns to Experiment Cells

Within the "Campaigns" section, you will map your active campaigns to the respective "Cell 1" (and any other cells) defined in your hypothesis. This ensures that the chosen campaigns are correctly associated with the treatment and control groups for accurate measurement.

### Step 5: Experiment Review

The final step before launching your experiment is a comprehensive review of all the configurations. This page provides a summary of your experiment design, data selection, market cohorts, and campaign mappings.

<Image align="center" src="https://files.readme.io/b2561385526a599be8ac63d71a650b1ab24719d4eef2637da4b0d10c883fc493-Experiment_review_page.png" />

On the review page, you will see a consolidated view of:

* **Cell Details**: Including the hypothesis, treatment type, minimum detectable lift, and additional spend.
* **Test Markets**: The selected markets and their market share.
* **Control Markets**: The detailed breakdown of the synthetic control group composition.
* **Time Series Decomposition**: A visual representation of observed values over time for both control and treatment groups.

Review all the details carefully. If everything looks correct, you can proceed to launch your experiment.