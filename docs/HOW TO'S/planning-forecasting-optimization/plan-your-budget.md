---
title: How to plan your optimal budget
excerpt: How to plan your budget to achieve more incremental revenue
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Problem Statement:

- In today’s competitive market, allocating your marketing budget efficiently is crucial to achieving your forecasted revenue goals. However, determining the optimal budget distribution across various channels and strategies remains a significant challenge due to the complex and nonlinear relationships between ad spend and revenue. Without a clear understanding of these relationships, you risk underinvesting in high-impact areas or overspending on low-return channels, ultimately falling short of your revenue targets.
- The scenario planner aims to address this challenge by providing a data-driven approach to budget planning. By leveraging historical data and advanced modeling techniques (like ridge regression), the tool helps you simulate different budget scenarios and forecast their potential impact on revenue. This enables you to make informed decisions and strategically allocate your resources to maximize return on investment (ROI) and achieve your forecasted revenue.

***

### How to Plan your budget to achieve your forecasted revenue:

- The first step for this is to **Create a plan**: The steps for creating a plan are mentioned [here](https://dash.readme.com/project/lifesight/v1.0/docs/how-to-build-a-plan) : 
- The **primary** parameters to consider when creating a plan are: 

[block:parameters]
{
  "data": {
    "h-0": "Fields                                                                                                                                                           ",
    "h-1": "Description",
    "0-0": "**Optimize Based on Period**",
    "0-1": "The selection should be made in alignment with your understanding of the business objectives and strategic goals.  \n  \nAlso, our MMM model provides the decomposition of **seasonality**, **trend**, **holiday** and **weekend** which you can find [here](https://docs.lifesight.io/docs/how-to-use-seasonality-trend-holiday-graph-to-understand-which-base-period-would-be-the-optimum-for-your-forecasting), this helps you understand the `Optimized Based on Period`.  \n  \nSome rules of thumb which can help you select the `Optimized Based on Period` value:  \n  \n1. **If the data is seasonal and there is a flat trend**: You take last year's same month as the base period.\n2. **If the data is seasonal and there is an additive trend**: You can either take last year's same month as the base period or the latest month as the base period.\n3. **If the data is not seasonal and there is an additive trend:** Take the latest month as the base period.\n4. **If the data is not seasonal and there is a flat trend:** Take the latest month as the base period.",
    "1-0": "**Forecast period**",
    "1-1": "We provide the functionality to forecast for the next:  \n  \n1. **Month**\n2. **Two Months**\n3. **Quarter**.",
    "2-0": "**Constraints**",
    "2-1": "We provide the various constraints:  \n  \n1. **Current** - The channel's optimised budget will be between 95% and 105% of the average value of the respective channel budget over the Optimize Based on Period.\n2. **Conservative** - The channel's optimised budget will be between 75% and 150% of the average value of the respective channel budget over the Optimize Based on Period.\n3. **Moderate**- The channel's optimised budget will be between 50% and 200% of the average value of the respective channel budget over the Optimize Based on Period.\n4. **Aggressive**- The channel's optimised budget will be between 1% and 499% of the average value of the respective channel budget over the Optimize Based on Period.\n5. **Manual**- The user can add the necessary constraints for the channel's budget"
  },
  "cols": 2,
  "rows": 3,
  "align": [
    "left",
    "left"
  ]
}
[/block]