---
title: Default Scenario
excerpt: Utilize default scenario to set targets and optimize campaigns to achieve them
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The **Default Scenario** in any plan acts as your strategic north star. It represents the primary, most crucial version of your marketing plan that you intend to follow and optimize against. By designating a Default Scenario, you define which set of goals, budgets, and constraints should be used as the baseline for generating powerful, data-driven recommendations.

Think of it as the "source of truth" for your marketing objectives, which the causal attribution and optimizer engines use to help you refine your campaigns and achieve your goals more effectively.

### Key Characteristics

* **Single Source of Truth:** It provides a clear baseline for performance comparison and optimization.
* **Drives Recommendations:** The platform's optimizer uses the budget, constraints, and forecasted KPIs from the Default Scenario to generate budget allocation recommendations.

> ⚠️ **Important**
>
> You can only have **one** Default Scenario for any given output KPI within a plan. If you set a new scenario as the default, the previous one will automatically lose its default status for that KPI.

### How to Identify the Default Scenario

You can easily identify the Default Scenario in two places within the Planner.

#### **On the Planner Homepage**

On the main Planner dashboard, a **star icon** (★) is displayed next to the name of any plan that contains a default scenario. This gives you a quick visual indicator of your primary plans.

<Image align="center" src="https://files.readme.io/512e663e8f445d98aa2b82fd4dd0fa90c1d56331cd91f8cda0a5372a3ffbbd69-Deafult_Scenario_-_Planner_home_page.png" />

#### **Inside a Plan**

When you open a plan, the scenario that is currently set as the default will have a **"Default Scenario"** label next to its name in the scenario selector dropdown.

### Setting or Changing the Default Scenario

You can set or update the Default Scenario at any time from within a plan.

1. Navigate to the **Planner** from the left-hand menu.
2. Click on the plan you wish to modify.
3. Inside the plan, locate the list of scenarios (e.g., Scenario 1, Scenario 2).
4. Hover over the scenario you wish to set as the new default.
5. Click the **star icon** (☆) that appears next to the scenario name.

<Image align="center" src="https://files.readme.io/bdf1e615ff583ed4714a76c5a67494923177d8ed41fa0661b95cb5e7ba348058-Default_Scenario_Selection_Indicator.png" />

The star will become filled (★), and the "Default Scenario" label will now point to your selection. This now becomes the new baseline for any platform-generated recommendations.

> ℹ️ **Note**
>
> While creating a new plan, a default scenario needs to be explicitly set. We recommend always reviewing and confirming this setting to ensure it aligns with your strategic goals.

### Impact on Recommendations and Optimization

Setting a Default Scenario is critical for leveraging Lifesight's optimization capabilities. Here’s how it works:

* The **Optimizer Engine** ingests the planned budget, constraints, and forecasted revenue/KPIs from your Default Scenario.
* It then compares this baseline against potential outcomes derived from our causal attribution models.
* Based on this comparison, the platform provides **Recommendations** on how to reallocate your budget across different platforms and channels to maximize your return on ad spend (ROAS) or other target KPIs.

Without a Default Scenario, the platform lacks a clear baseline to compare against, limiting its ability to provide tailored and effective optimization advice.

<br />

### FAQs

**Q: What happens if no default scenario is set in my plan?**\
A: While the first scenario is often set as default automatically, if no scenario is explicitly marked as the default, the platform will be unable to generate optimized budget recommendations for that plan, as it lacks a "source of truth" to use as a baseline.

**Q: Can I change the default scenario after a plan is already running?**\
A: Yes, you can change the Default Scenario at any time. When you select a new default, the platform will immediately start using that scenario's data as the new baseline for all future recommendations and forecasts.

**Q: I have two scenarios targeting "Revenue" as the KPI. Can I make both of them the default?**\
A: No. You can only have one designated Default Scenario per output KPI. Setting a second scenario that targets "Revenue" as the default will automatically remove the default status from the first one.