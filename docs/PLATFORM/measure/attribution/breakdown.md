---
title: Breakdown
excerpt: >-
  Analyse incremental metrics and get causal recommendations at a channel,
  campaign, ad group and ad level.
deprecated: false
hidden: true
metadata:
  robots: index
next:
  pages:
    - slug: attribution-metrics-guide
      title: Attribution metrics guide
      type: basic
---
The **Breakdown** tab is your primary interface for conducting in-depth campaign and ad performance analysis on the Lifesight Platform. It allows you to move beyond high-level summaries and investigate the effectiveness of your marketing efforts at the most granular levels—from channels down to individual ads. Use this view to understand performance drivers, compare predicted and incremental impact, and make data-driven budget allocation decisions.

### When to Use the Breakdown Tab

This feature is essential for a variety of common analysis tasks. Use the Breakdown tab when you need to:

* Analyze and compare the performance of different marketing channels (e.g., Google, Facebook, TikTok) side-by-side.
* Drill down into a specific channel to evaluate the effectiveness of its individual campaigns, ad groups, or ads.
* Review the platform's automated **Tactics** for specific marketing activities.
* Compare the **Predicted Revenue (pRevenue)** against the **Incremental Revenue (iRevenue)** to understand the true lift from your marketing spend.
* Identify top-performing and under-performing assets to inform your budget optimization and reallocation strategies.

### Navigating the Interface

The Breakdown tab consists of three main components: Primary Filters, the Performance Chart, and the Breakdown Table.

<Image align="center" src="https://files.readme.io/a4646ce1e74750392c5ce867348f119445713784c9e14e5fbb82f8b0fd299369-Attribution_Breakdown_tab.png" />

<br />

#### Primary Filters (Attribution Period & Model)

These two filters at the top of the page set the overall context for your analysis.

* **Attribution Period:** A date-range selector that defines the time frame for all data displayed in the chart and table below.
* **Attribution Model:** A dropdown menu to select the model used for attributing conversions.

<Callout icon="📘" theme="info">
  The **Causal** model uses advanced statistical techniques to determine the true, incremental impact of your marketing efforts. While the other touch-based attribution models would offer aggregated platform metrics and directional budget insights, the Causal attribution model presents incremental metrics and precise budget recommendations.
</Callout>

#### Performance Chart

This interactive chart provides a visual representation of your key metrics over the selected attribution period.

* **Metric:** The primary metric you want to plot on the Y-axis (e.g., `iRevenue`).
* **Compare To:** A secondary metric to plot for comparison (e.g., `Ad Spend`).
* **Granularity:** The time interval for the X-axis (e.g., `Daily`, `Weekly`, `Monthly`).

You can toggle the visibility of the chart using the **Hide Chart** switch located above the breakdown table.

#### The Breakdown Table

This is the core of the Breakdown tab, where you can analyze your performance data at multiple levels of detail.

<Image align="center" src="https://files.readme.io/ff1e8d3df482b1c6e1897c6f9f4aba19edd19ff11161ae410a5863cd89e1ed5a-Causal_Attribution_-_Channel_Breakdown_-_Campaigns.png" />

Use the tabs at the top of the table to switch between different views:

* **Channels:** A high-level view comparing the performance of each marketing channel.
* **Tactics:** Groups campaigns by the defined tactics on the platform (e.g., Meta TOF, Meta ASC, etc.).
* **Campaigns:** A detailed view of every campaign across all channels.
* **Ad Groups:** Drills down further to the ad group level.
* **Ads:** Provides the most granular view, showing performance data for each individual ad.

<br />
