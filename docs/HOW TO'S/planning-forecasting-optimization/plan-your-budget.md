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

* In today’s competitive market, allocating your marketing budget efficiently is crucial to achieving your forecasted revenue goals. However, determining the optimal budget distribution across various channels and strategies remains a significant challenge due to the complex and nonlinear relationships between ad spend and revenue. Without a clear understanding of these relationships, you risk underinvesting in high-impact areas or overspending on low-return channels, ultimately falling short of your revenue targets.
* The scenario planner aims to address this challenge by providing a data-driven approach to budget planning. By leveraging historical data and advanced modeling techniques (like ridge regression), the tool helps you simulate different budget scenarios and forecast their potential impact on revenue. This enables you to make informed decisions and strategically allocate your resources to maximize return on investment (ROI) and achieve your forecasted revenue.

***

### How to Plan your budget to achieve your forecasted revenue:

* The first step for this is to **Create a plan**: The steps for creating a plan are mentioned [here](https://dash.readme.com/project/lifesight/v1.0/docs/how-to-build-a-plan) : 
* The **primary** parameters to consider when creating a plan are: 

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Fields                                                                                                                                                           
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        **Optimize Based on Period**
      </td>

      <td style={{ textAlign: "left" }}>
        The selection should be made in alignment with your understanding of the business objectives and strategic goals.  

        Also, our MMM model provides the decomposition of **seasonality**, **trend**, **holiday** and **weekend** which you can find [here](https://docs.lifesight.io/docs/how-to-use-seasonality-trend-holiday-graph-to-understand-which-base-period-would-be-the-optimum-for-your-forecasting), this helps you understand the `Optimized Based on Period`.  

        Some rules of thumb which can help you select the `Optimized Based on Period` value:  

        1. **If the data is seasonal and there is a flat trend**: You take last year's same month as the base period.
        2. **If the data is seasonal and there is an additive trend**: You can either take last year's same month as the base period or the latest month as the base period.
        3. **If the data is not seasonal and there is an additive trend:** Take the latest month as the base period.
        4. **If the data is not seasonal and there is a flat trend:** Take the latest month as the base period.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Forecast period**
      </td>

      <td style={{ textAlign: "left" }}>
        We provide the functionality to forecast for the next:  

        1. **Month**
        2. **Two Months**
        3. **Quarter**.
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        **Constraints**
      </td>

      <td style={{ textAlign: "left" }}>
        We provide the various constraints:  

        1. **Current** - The channel's optimised budget will be between 95% and 105% of the average value of the respective channel budget over the Optimize Based on Period.
        2. **Conservative** - The channel's optimised budget will be between 75% and 150% of the average value of the respective channel budget over the Optimize Based on Period.
        3. **Moderate**- The channel's optimised budget will be between 50% and 200% of the average value of the respective channel budget over the Optimize Based on Period.
        4. **Aggressive**- The channel's optimised budget will be between 1% and 499% of the average value of the respective channel budget over the Optimize Based on Period.
        5. **Manual**- The user can add the necessary constraints for the channel's budget
      </td>
    </tr>
  </tbody>
</Table>
