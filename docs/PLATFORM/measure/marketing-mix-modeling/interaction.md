---
title: Interaction
deprecated: false
hidden: true
metadata:
  robots: index
---
The **Interaction** tab provides a crucial, in-depth view of how your marketing channels influence one another. Marketing efforts rarely operate in a vacuum; they can amplify each other (**synergy**) or compete for the same conversions (**cannibalization**).

Understanding these relationships is key to moving beyond siloed channel optimization and creating a truly unified marketing strategy. By quantifying these cross-channel effects, you can make more intelligent budget allocation decisions, reduce wasted spend, and maximize your overall marketing ROI.

### Understanding Interaction Effect Types

The platform categorizes the relationship between any two marketing variables into four distinct types. These are calculated based on how the presence of one channel impacts the effectiveness of another.

* **Strong Synergy**: Occurs when two channels have a significant and mutually beneficial impact. For example, a TV campaign may significantly boost the number of conversions from Branded Paid Search as viewers actively look for your brand online after seeing an ad. Investing in both simultaneously creates an amplified effect.
* **Weak Synergy**: Indicates a positive but less pronounced interaction between two channels. While they help each other, the combined lift is moderate.
* **Strong Cannibalization**: This happens when two channels heavily compete for the same audience and conversions, leading to inefficiency. For instance, running two distinct social media campaigns that target the exact same user demographic with a similar message can lead to one campaign "stealing" conversions from the other.
* **Weak Cannibalization**: A minor negative or overlapping effect between channels. The competition exists but is not severe enough to cause a major drain on efficiency.

### Navigating the Interactions Tab

To begin your analysis, you can refine the data shown on the tab using several filters:

* **Date Range**: Select the specific time period you want to analyze for interaction effects.
* **Version**: Choose the model version you wish to inspect.
* **Channel Filter**: Narrow down the view to see interactions related to specific channels.
* **Effect Type Filter**: Isolate the data to view only certain types of interactions (e.g., show only channels with **Strong Synergy**).

### Interpreting the Interaction Data

The platform offers two primary views for analyzing interaction effects, allowing you to go from a high-level overview to a detailed, actionable list.

#### Interaction Matrix View

The **Interaction Matrix** provides a high-level, color-coded heatmap of how all your marketing variables interact with each other. This view is excellent for quickly spotting the most significant relationships in your marketing mix.

* **How to Read It**: Each row and column represents a marketing variable (like 'Meta TOF Spend' or 'Klaviyo Unique Clicks'). The cell where a row and column intersect shows the interaction effect between those two variables.
* **Color Coding**:
  * **Green**: Indicates **Synergy**. The deeper the green, the stronger the positive interaction.
  * **Red**: Indicates **Cannibalization**. The deeper the red, the stronger the negative interaction.
* **Cell Value**: The number inside the cell is the **Interaction Factor**, which quantifies the strength of the relationship. A high positive number means strong synergy, while a large negative number means strong cannibalization.

#### Interaction Details View

The **Interaction Details** view provides a comprehensive, sortable list of every interaction pair, along with a clear recommendation for action. This view is ideal for tactical decision-making.

The table contains the following columns:

* **Interaction Variables**: The pair of marketing channels or activities being analyzed (e.g., `TV Spend + Tiktok Spend`).
* **Interaction Effect**: The qualitative label for the relationship (e.g., 'Strong Cannibalization', 'Strong Synergy').
* **Interaction Factor**: The specific numerical score that quantifies the strength and direction of the interaction.
* **Recommendation**: A clear, actionable suggestion based on the interaction effect.

### Taking Action on Insights

The ultimate goal of this analysis is to inform your strategy. The recommendations provided in the **Interaction Details** view are designed to be a direct input for your budget planning and optimization efforts.

> [!NOTE]
> Use these insights to optimize budget splits _between_ channels, not just _within_ them. This is the key to unlocking the full potential of your marketing mix.

#### Responding to Synergy

* **Recommendation**: "Increase both together to amplify effect."
* **What it means**: When you identify two channels like `{{channel_a}}` and `{{channel_b}}` that have strong synergy, you should treat them as a pair. Planning to increase your TV spend? You should simultaneously plan for a corresponding increase in your branded search budget to capture the new demand you're creating. Scaling them in tandem produces a greater return than scaling either one in isolation.

#### Addressing Cannibalization

* **Recommendation**: "Choose one to scale; avoid increasing both."
* **What it means**: If you find that `{{channel_a}}` and `{{channel_b}}` are cannibalizing each other, investing more in both at the same time will likely lead to diminished returns. You are paying twice to reach the same user. The recommendation is to analyze the individual ROI of each channel and prioritize scaling the more efficient one while maintaining or reducing investment in the other for that specific target segment.
