---
title: Channel Deepdive
excerpt: >-
  Understand revenue contribution trends and investigate spending patterns for a
  Channel or Tactic
deprecated: false
hidden: false
metadata:
  robots: index
---
## 1. Overview

The **Channel Deepdive** tab  provides a granular view of your marketing channel performance. Its primary purpose is to help you move beyond high-level summaries and understand the specific spending patterns, revenue generation, and efficiency of each individual channel.

Use this tab to answer critical questions such as:

* Which channel is generating the most revenue?
* What is the typical spend for my key channels, and are there any unusual deviations?
* Is there a clear relationship between how much I spend on a channel and the revenue it produces?
* How does the delayed impact of advertising (ad lag) affect a channel's perceived performance?

## 2. Key Components and Metrics

The Channel Deepdive tab is composed of several powerful widgets and visualizations designed to give you a comprehensive understanding of your channel data.

### Channel Performance Analysis

This central view breaks down performance by individual channel. For each channel, you can analyze:

* **Total Revenue:** The total revenue attributed to the channel within the selected timeframe.
* **Total Spend:** The total amount spent on the channel.
* **Spend Analysis:** This provides context for your spending habits by showing the **Minimum**, **Average**, and **Maximum** spend observed for the channel across the different time periods in your data.

### Outlier Analysis

This feature automatically flags unusual spending activity to help you identify potential issues or opportunities.

* **Outliers:** Data points that fall outside the expected range of spending for a channel.
* **Analysis Levels:** The platform highlights these outliers at multiple levels of granularity: **Overall**, **Yearly**, **Quarterly**, and **Monthly**, allowing you to pinpoint exactly when the unusual activity occurred.

### Spend vs. Revenue Chart

This is a standard scatter plot that helps you visualize the direct relationship between spend and revenue for a selected channel.

* **X-Axis:** Represents the **Spend**.
* **Y-Axis:** Represents the **Revenue**.
* **Interpretation:** Ideally, you want to see a positive correlation where an increase in spend leads to a corresponding increase in revenue. This chart helps you identify the point of diminishing returns, where additional spend no longer generates proportional revenue.

### Spend vs. Shifted Revenue Chart

This advanced chart provides a more accurate view of performance by accounting for the natural delay between advertising spend and customer conversion.

* **Shifted Revenue:** This metric calculates revenue by applying a **7-day lookback window**. This means it correlates the spend from a specific day with the revenue generated over the following 7 days, capturing the lag effect of your ads.
* **Purpose:** By comparing this chart to the standard **Spend vs. Revenue** chart, you can better understand the true impact of channels that may have a longer consideration cycle.

## 3. How to Interpret and Use the Insights

The data in the Channel Deepdive tab is designed to be actionable. Here are a few ways you can use these insights to inform your strategy:

* **Budget Optimization:** Use the channel performance data to reallocate budget from lower-performing channels to those with higher revenue generation and a stronger spend-to-revenue correlation.
* **Performance Monitoring:** Use the **Outlier Analysis** to investigate sudden spikes or drops in spending. This can help you catch campaign configuration errors or identify unexpectedly successful tactics.
* **Strategic Planning:** Analyze the **Spend vs. Shifted Revenue** chart to justify investment in channels that may not show immediate returns but prove valuable over a slightly longer timeframe.

## 4. Frequently Asked Questions (FAQ)

**Q: What is the definition of 'Shifted Revenue' and why is it important?**\
A: **Shifted Revenue** is a metric that accounts for ad lag by correlating spend with the revenue generated over a subsequent 7-day period. It is important because many customers do not convert immediately after seeing an ad. This metric provides a fairer and more accurate assessment of a channel's performance by capturing delayed conversions.

**Q: How does the platform determine if a data point is an outlier?**\
A: Outliers are identified using a proprietary statistical model that analyzes historical spending patterns for each channel. Any spend that deviates significantly from the established norm is flagged as an outlier.

**Q: Can I change the 7-day window for the Spend vs. Shifted Revenue chart?**\
A: Currently, the 7-day window is a fixed setting designed to provide a standardized view of ad lag effects based on industry benchmarks.