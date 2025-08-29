---
title: Configurations
excerpt: >-
  Configure rules, attribution weights, profit calcualtion metrics and casual
  attribution settings 
deprecated: false
hidden: true
metadata:
  robots: index
---
The **Configurations** section is the control center for organizing and classifying your marketing data within the Lifesight Platform. Properly configuring these settings is a crucial first step to ensure your data is correctly grouped, labeled, and prepared for attribution and profitability insights. This section allows you to translate raw data from various sources into a structured format, creating a single source of truth suitable for actionable insights.

Each tab within this section provides a specific set of tools to manage how the platform interprets your marketing activities.

<br />

### Mapper

The **Mapper** tab is your primary interface for viewing and classifying all incoming campaign data. The platform automatically ingests data from your connected sources and displays it here, showing columns such as `Campaign ID`, `Campaign Name`, `Source`, and `Objective`.

Your main task in this tab is to ensure that every campaign is assigned a **Tactic**. While many campaigns will be classified automatically based on rules, you can use the dropdown menu in the `Tactic` column to manually assign a classification to any unmapped campaigns.

<br />

### UTM Tags

The **UTM Tags** tab provides a standardized framework for creating and managing your UTM tags across all major ad platforms. Its primary goal is to ensure your tracking data is consistent and structured correctly before it even enters the Lifesight platform.

While the platform does not directly generate or modify UTMs within your ad accounts, it provides powerful, platform-specific templates. You can use these templates to construct consistent UTMs, which can then be copied and pasted directly into your live ad campaigns.

By using these standardized templates, you ensure that the campaign data flowing into the Lifesight UMM Platform is clean and uniform. This greatly improves the accuracy of automatic classification in the Mapper tab and reduces the need for manual adjustments.

<br />

### Rules & Labels

The **Rules & Labels** tab provides a more powerful and flexible way to create custom classifications. While the UTM Tags tab focuses on UTMs, this section allows you to build rules based on any field, such as `Campaign Name`, `Source`, or `Objective`.

You can create custom labels and use complex, multi-conditional logic to apply them. This is essential for creating the granular classifications needed for better causal attribution insights and recommendations.

**Example:**

* **Rule:** If `Source` is 'facebook' **AND** `Campaign Name` contains 'video_awareness', then apply the custom label 'Upper Funnel Video'.

<br />

### Algorithmic

This tab is an advanced section for managing the parameters and weights that power the platform's algorithmic attribution models. It allows you to input "prior beliefs" into the model, which can help guide the attribution calculations based on your business knowledge or previous analyses.

<Callout icon="🚧" theme="warn">
  #### [!WARNING]

  The settings in the Algorithmic tab directly influence the core calculations of your measurement model. These settings should only be adjusted by users with a deep understanding of the underlying models. Please consult with your Lifesight data science team before making any changes.
</Callout>

<br />

### Causal

The **Causal** tab contains settings related to the platform's causal inference models. This is where you can configure parameters for causal attribution. These models help you understand the true causal impact of your marketing efforts by indicating which campaigns have a causal impact in helping you achieve your revenue or ROAS goals.

<br />

### Costs

Accurate performance measurement is impossible without accurate cost data. The **Costs** tab is where you can input and manage the fixed and variables costs of running your business. This will help in calculating profitability of channels,
