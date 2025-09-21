---
title: Creating a plan
excerpt: Step-by-step guide to create a plan
deprecated: false
hidden: true
metadata:
  robots: index
next:
  pages:
    - slug: intrepreting-a-budget-plan
      title: Intrepreting a plan
      type: basic
---
The Planner allows you to simulate and forecast the potential impact of different marketing budget allocations. By creating various scenarios based on your existing Marketing Mix Models, you can make informed, data-driven decisions to optimize spend and maximize revenue.

> 📘 Use the interactive demo below to guide you through each step of the plan creation process
>
> <HTMLBlock>{`
> <div>
>   <script async src="https://js.storylane.io/js/v2/storylane.js"></script>
>   <div class="sl-embed" style="position:relative;padding-bottom:calc(56.21% + 25px);width:100%;height:0;transform:scale(1)">
>     <iframe loading="lazy" class="sl-demo" src="https://lifesight.storylane.io/demo/l2jzclomnair?embed=inline" name="sl-embed" allow="fullscreen" allowfullscreen style="position:absolute;top:0;left:0;width:100%!important;height:100%!important;border:1px solid rgba(63,95,172,0.35);box-shadow: 0px 0px 18px rgba(26, 19, 72, 0.15);border-radius:10px;box-sizing:border-box;"></iframe>
>   </div>
> </div>
> `}</HTMLBlock>

### Step 1: Create a New Plan

To create a new budget plan, start from the main Planner page and click the **Create Plan** button to begin the scenario configuration process.

<br />

<Image align="center" src="https://files.readme.io/ce0dd290d359f64f41a8531e8d5d7c0b377b9225a8f792beb72daa4c66cafab2-Planner_Home.png" />

<br />

> 👍 You can also create a plan directly from a specific Marketing Mix Model. Navigate to the **Marketing Mix Models** page, select a model, and click the **Create Plan** button on the top-right.

### Step 2: Configure the Scenario

After starting a new plan, you will be taken to the scenario configuration page. Here, you will define the parameters for your budget simulation.

#### Selecting the Base Model

From the **Select Model** dropdown, choose the successfully calibrated Marketing Mix Model you wish to use as the foundation for your plan.

<Image align="center" width="350px" src="https://files.readme.io/49b2a998cadb2f3123f6c7959f66b25a05cd3c4c2288097c1db622854ead0893-Planner_-_Model_Selector.png" />

<br />

<Callout icon="🚧">
  To get precise predictions and budget allocation recommendations, ensure the model you select has been fed the latest data. 
</Callout>

#### Setting the Goal, Forecast, and Basis Period

<Image align="center" src="https://files.readme.io/6153457e981f28dbd5ddbefafeeee5914901f907aa3fa00ff06ca7022335cd5b-Planner_-_Scenario_inputs_.png" />

<br />

Input the following parameters to generate the first scenario for the plan (which will be fixed across the other scenarios added in the next step)

* **Goal**: Select the Goal that needs to be accomplished with the plan. _Target Budget_ is typically selected for finding the best allocation for a specific budget and _Target KPI_ is selected for chasing a KPI (eg: Revenue, orders, etc.) goal.
* **Set Forecast and Basis Periods**: Select the timeframe for the simulation by selecting a **"Forecast for"** period (e.g., Quarter) and the specific **"Optimized based on"** date range. This basis period tells the model which historical conditions are most similar to your intended forecast period.
* **Target Budget**: In the Target Budget field, enter the total amount you want the planner to allocate.
* **Custom Pacing**: Toggle the custom pacing button to unevenly spread your budget across your plan. Refer to  [Custom Budget Pacing](https://docs.lifesight.io/update/docs/custom-budget-pacing#/) for a detailed guide

#### Defining Spend Constraints

Constraints set realistic boundaries for how the scenario planner can allocate your budget. You can use presets or define them manually.

The available modes are:

* **Current**: Retains the current spend levels and sets the upper & lower limits to ±5% from the current spend levels.
* **Conservative**: Narrows the spending range, keeping it close to current levels.
* **Moderate**: Allows for more flexibility in budget allocation than Conservative mode.
* **Aggressive**: Provides the widest range for budget allocation, allowing the model to explore more dramatic shifts in spending.
* **Manual**: Allows you to set specific **Lower Limit** and **Upper Limit** spend values for each individual channel in the table below.

<br />

> ℹ️ **How Constraints are Determined**
>
> * **For causally calibrated channels**: The scenario planner uses predefined lower and upper budget limits. These limits are used to run revenue simulations **without modifying the overall Target Budget** you entered.
> * **For causally uncalibrated channels**: The planner applies a **±10% change** to the current channel budget allocation. This ensures that the predictions are reliable and backed by clear historical data patterns.

### Step 3: Run the Scenario

Once you have configured the goal, budget, and constraints to your satisfaction, click the **Run Scenario** button in the top-right corner. This will initiate the simulation process, and the platform will use your inputs to calculate the optimal budget allocation and forecast the results.

<br />
