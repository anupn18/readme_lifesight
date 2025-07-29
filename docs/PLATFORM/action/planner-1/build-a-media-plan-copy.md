---
title: Creating a Budget plan
excerpt: Step-by-step guide to create a plan
deprecated: false
hidden: true
metadata:
  robots: index
---
The Budget Plan feature in the Lifesight UMM Platform allows you to simulate and forecast the potential impact of different marketing budget allocations. By creating various scenarios based on your existing Marketing Mix Models, you can make informed, data-driven decisions to optimize spend and maximize revenue.

### Step 1: Create a New Plan

To create a new budget plan, start from the main Planner page.

<Image align="center" src="https://files.readme.io/ce0dd290d359f64f41a8531e8d5d7c0b377b9225a8f792beb72daa4c66cafab2-Planner_Home.png" />

1. Navigate to the **Planner** section from the main platform menu.
2. Click the **Create Plan** button to begin the scenario configuration process.

> 👍 You can also create a plan directly from a specific Marketing Mix Model. Navigate to the **Marketing Mix Models** page, select a model, and click the **Create Plan** button on the top-right.

### Step 2: Configure the Scenario

After starting a new plan, you will be taken to the scenario configuration page. Here, you will define the parameters for your budget simulation.

#### Selecting the Base Model

From the **Select Model** dropdown, choose the successfully calibrated Marketing Mix Model you wish to use as the foundation for your plan.

<br />

#### Setting the Goal, Forecast, and Basis Period

<Image align="center" src="https://files.readme.io/a72206b9d0dad933c9c34e3de8baf9b8d8a302db3ae53bf77f3a4cdc9b90a563-Scenario_configuration_page.png" />

<br />

In the **Goal** section, define the primary objective, budget, and timeframes for your plan.

* **Target Budget**: In the Target Budget field, enter the total amount you want the planner to allocate.
* **Set Forecast and Basis Periods**: Select the timeframe for the simulation by selecting a **"Forecast for"** period (e.g., Quarter) and the specific **"Optimized based on"** date range. This basis period tells the model which historical conditions are most similar to your intended forecast period.

#### Defining Spend Constraints

Constraints set realistic boundaries for how the scenario planner can allocate your budget. You can use presets or define them manually.

The available modes are:

* **Current**: Uses the current spend levels as a baseline.
* **Conservative**: Narrows the spending range, keeping it close to current levels.
* **Moderate**: Allows for more flexibility in budget allocation than Conservative mode.
* **Aggressive**: Provides the widest range for budget allocation, allowing the model to explore more dramatic shifts in spending.
* **Manual**: Allows you to set specific **Lower Limit** and **Upper Limit** spend values for each individual channel in the table below.

> ℹ️ **How Constraints are Determined**
>
> * **For causally calibrated channels**: The scenario planner uses predefined lower and upper budget limits. These limits are used to run revenue simulations **without modifying the overall Target Budget** you entered.
> * **For causally uncalibrated channels**: The planner applies a **±10% change** to the current channel budget allocation. This ensures that the predictions are reliable and backed by clear historical data patterns.

### Step 3: Run the Scenario

Once you have configured the goal, budget, and constraints to your satisfaction, click the **Run Scenario** button in the top-right corner. This will initiate the simulation process, and the platform will use your inputs to calculate the optimal budget allocation and forecast the results.

### Next Steps

After running the scenario, the platform will generate a detailed forecast. For a complete guide on how to analyze and understand this output, refer Interpreting Scenario Results page.