---
title: '[WIP] Configurations'
deprecated: false
hidden: true
metadata:
  robots: index
---
The **Configurations** section is the control center for organizing and classifying your marketing data within the Lifesight Platform. Properly configuring these settings is a crucial first step to ensure your data is correctly grouped, labeled, and prepared for attribution and profit insights. This section allows you to translate raw data from various sources into a structured format, creating a single source of truth suitable for actionable insights.

Each tab within this section provides a specific set of tools to manage how the platform interprets your marketing activities.

***

### Mapper

The **Mapper** tab is your primary interface for viewing and classifying all incoming campaign data. The platform automatically ingests data from your connected sources and displays it here, showing columns such as `Campaign ID`, `Campaign Name`, `Source`, and `Objective`.

Your main task in this tab is to ensure that every campaign is assigned a **Tactic**. While many campaigns will be classified automatically based on rules, you can use the dropdown menu in the `Tactic` column to manually assign a classification to any unmapped campaigns.

![The Mapper tab interface shows a table of campaigns with columns for Campaign ID, Campaign Name, Source, and a dropdown for assigning a Tactic.](https://storage.googleapis.com/maker-studio-project-media-prod/1167448d-697e-4050-b98a-a4305f889981/images/Configurations%20-%20Tactic%20Mapper%20Page.jpg)

***

### UTM Tags

The **UTM Tags** tab allows you to automate the classification process seen in the Mapper. Here, you can create rules that scan your campaign UTM parameters for specific text or patterns. When a match is found, the rule automatically assigns the corresponding Tactic, Label, or other classification.

**Example:**

* **Rule:** If `utm_campaign` contains "brand\_search", then assign the Tactic "Branded Search".

Using UTM Tag rules significantly reduces the need for manual mapping and ensures consistency across your campaigns.

***

### Rules & Labels

The **Rules & Labels** tab provides a more powerful and flexible way to create custom classifications. While the UTM Tags tab focuses on UTMs, this section allows you to build rules based on any field, such as `Campaign Name`, `Source`, or `Objective`.

You can create custom labels and use complex, multi-conditional logic to apply them. This is essential for creating the granular segments needed for in-depth analysis and modeling.

**Example:**

* **Rule:** If `Source` is 'facebook' **AND** `Campaign Name` contains 'video\_awareness', then apply the custom label 'Upper Funnel Video'.

***

### Algorithmic

This tab is an advanced section for managing the parameters and weights that power the platform's algorithmic attribution models. It allows you to input "prior beliefs" into the model, which can help guide the attribution calculations based on your business knowledge or previous analyses.

> \[!WARNING]\
> The settings in the Algorithmic tab directly influence the core calculations of your measurement model. These settings should only be adjusted by users with a deep understanding of the underlying models. Please consult with your Lifesight data science team before making any changes.

***

### Causal

The **Causal** tab contains settings related to the platform's causal inference models. This is where you can configure parameters for methodologies like incrementality measurement and uplift modeling. These models help you understand the true causal impact of your marketing efforts by comparing campaign performance against control groups, a key component of a unified measurement approach.

***

### Costs

Accurate performance measurement is impossible without accurate cost data. The **Costs** tab is where you can upload, manage, and verify the spend associated with all your marketing campaigns. Ensuring this data is complete and up-to-date is critical for calculating key metrics like Return on Investment (ROI) and for making informed budget allocation decisions.