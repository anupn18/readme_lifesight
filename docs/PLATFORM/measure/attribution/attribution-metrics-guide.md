---
title: Attribution metrics guide
excerpt: >-
  Understand the definition for every metric tracked in your Attribution
  dashboard.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Attribution metrics help measure and analyze the impact of marketing efforts across different channels. These metrics allow businesses to understand which touchpoints contribute most to conversions, enabling more informed decisions about resource allocation and marketing strategies.

<br />

## Summary metrics

[block:parameters]
{
  "data": {
    "h-0": "",
    "h-1": "",
    "h-2": "",
    "0-0": "Attributed Revenue",
    "0-1": "The total revenue generated from customer interactions that can be directly attributed to your marketing efforts.",
    "0-2": "-",
    "1-0": "MER",
    "1-1": "MER (Marketing Efficiency Ratio) compares the total revenue generated to the marketing spend. A higher MER indicates more efficient marketing spend.",
    "1-2": "Attributed Revenue / Total Marketing Spends",
    "2-0": "NC Revenue ",
    "2-1": "(New Customer Revenue is the total revenue generated specifically from new customers acquired through your marketing efforts.",
    "2-2": "-",
    "3-0": "NC ROAS",
    "3-1": "New Customer Return On Ad Spend is similar to ROAS, but focuses on the return on ad spend specifically for new customers acquired.",
    "3-2": "NC Revenue / Ad Spend",
    "4-0": "NC MER",
    "4-1": "New Customer Marketing Efficiency Ratio is similar to MER, but focuses on the efficiency of marketing spend for acquiring new customers.",
    "4-2": "NC Revenue / Ad Spend",
    "5-0": "Att. Revenue Error",
    "5-1": "Revenue Attribution Error Range represents the potential discrepancy in revenue attribution between platform-reported revenue and Lifesight's calculated revenue.  \n• Min Value: Indicating the minimum possible shortfall in revenue attribution.  \n• Max Value: Indicating the maximum possible over-attribution, accounting for direct traffic.",
    "5-2": "Min Value = platformRevenue - Attributed Revenue  \n  \nMax Value = (Direct + platformRevenue) - Attributed Revenue",
    "6-0": "NC AOV",
    "6-1": "New Customer Average Order Value is the average amount spent per order by new customers.",
    "6-2": "-",
    "7-0": "Ad Spend",
    "7-1": "The total amount of money you've invested in marketing campaigns across all channels during the selected timeframe.",
    "7-2": "-",
    "8-0": "Impressions",
    "8-1": "The number of times your paid marketing message is displayed, regardless of whether a user clicks on it.",
    "8-2": "-",
    "9-0": "Platform Revenue",
    "9-1": "",
    "9-2": "",
    "10-0": "Platform Orders",
    "10-1": "",
    "10-2": ""
  },
  "cols": 3,
  "rows": 11,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

## Engagement metrics

| Metric name | Definition | Formula |
| :---------- | :--------- | :------ |
| Impressions |            |         |
| Clicks      |            |         |

<br />

## Conversion metrics

| Metric name        | Definitions                                                                                                                                                                                         | Formula                                    |
| :----------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------- |
| Visits             | The total number of times users visit your website or landing page.                                                                                                                                 |                                            |
| CPA (Visits)       | The average cost of acquiring a new website visitor through your marketing efforts.                                                                                                                 | Ad Spend / Visits                          |
| Signups            | The number of users who have registered for your service or created an account on your website.                                                                                                     | -                                          |
| CPA (Signups)      | The average cost of acquiring a new signup through your marketing efforts.                                                                                                                          | Ad Spend / Signups                         |
| Add to Carts       | The number of times a product or service is added to a user's shopping cart.                                                                                                                        | -                                          |
| CPA (Add to Carts) | The average cost of getting a user to add a product or service to their shopping cart.                                                                                                              | Ad Spend / Add to Cart                     |
| iROAS              | Incremental Return On Ad Spend measures the additional revenue generated from advertising efforts compared to the incremental ad spend, focusing on the true impact of ads.                         | Incremental Revenue / Incremental Ad Spend |
| pOrders            | Platform Orders refer to the number of orders attributed to a specific advertising or ecommerce platform (such as Google, Facebook, or Amazon) based on tracking and attribution data.              | -                                          |
| pCPA (Orders)      | Platform Cost Per Acquisition is the average cost incurred to acquire a customer or achieve a conversion (such as a sale, signup, or other desired action) through a specific advertising platform. | Platform Spend / Platform orders           |

<br />

## Revenue metrics

| Metric name     | Definitions                                                                  | Formula                |
| :-------------- | :--------------------------------------------------------------------------- | :--------------------- |
| AOV             | Average Order Value is the average amount spent per order by your customers. | -                      |
| pRevenue        | Platform Revenue is the revenue reported by a specific ad channel            | -                      |
| UTM Revenue     | Refers to the revenue captured by Lifesight                                  | -                      |
| Channel vs UTM  | Compares the differences between UTM and Platform reported revenue           | pRevenue - UTM Revenue |
| UTM New Revenue | Refers to the new revenue captured by Lifesight                              | -                      |

<br />

## Purchases

[block:parameters]
{
  "data": {
    "h-0": "Metric name",
    "h-1": "Definitions",
    "h-2": "Formula",
    "0-0": "Purchases",
    "0-1": "Number of purchases events completed",
    "0-2": "",
    "1-0": "New Purchases",
    "1-1": "Number of new purchases events completed",
    "1-2": "",
    "2-0": "Cost Per Order",
    "2-1": "Cost Per Order",
    "2-2": "Ad spend / Order count",
    "3-0": "CAC",
    "3-1": "Customer Acquisition Cost is the average cost of acquiring a new customer, considering all marketing and sales expenses.",
    "3-2": "-",
    "4-0": "LTV/CAC Ratio",
    "4-1": "The LTV/CAC ratio measures the efficiency of customer acquisition by comparing the lifetime value (LTV) of a customer to the cost of acquiring that customer (CAC).  \n  \nAPV = Average Purchase Value = (total revenue / number of purchases) at the channel level  \n• APF = Average Purchase Frequency = (number of purchases / number of distinct customers) at the channel level  \n• CL = Customer Lifetime = The average duration from first purchase to last purchase across all customers in months",
    "4-2": "LTV = APV x APF x CL"
  },
  "cols": 3,
  "rows": 5,
  "align": [
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

## Spend

| Metric name | Definitions    | Formula |
| :---------- | :------------- | :------ |
| Spend       | Channel spends | -       |

<br />

## ROAS

| Metric name | Definitions                                                                                                                                  | Formula                                |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------- |
| ROAS        | A metric that shows the overall effectiveness of digital ad efforts by comparing the total revenue generated from ads to the total ad spend. | Attributed Revenue from ads / Ad Spend |
| pROAS       | Platform reported ROAS values                                                                                                                | Platform revenue / Platform spend      |
| UTM ROAS    | Lifesight reported ROAS values                                                                                                               |                                        |
| UTM NC ROAS | Lifesight reported ROAS for new customers                                                                                                    |                                        |

<br />

## Time to Convert

| Metric name     | Definitions                                                                                                                                                                                                                                                       |
| :-------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Conversion Rate | The percentage of visitors who complete a desired action on a website or app.                                                                                                                                                                                     |
| Average         | Defined as the mean time it took for a conversion event to occur from when the user landed on the website from an ad channel, averaged across all conversions for that specific ad channel. It helps identify which channels are driving the fastest conversions. |
| 25th Percentile | Represents the time below which 25% of all conversion events occur for an ad channel                                                                                                                                                                              |
| 50th Percentile | Represents the time below which 50% of all conversion events occur for an ad channel                                                                                                                                                                              |
| 75th Percentile | Represents the time below which 75% of all conversion events occur for an ad channel                                                                                                                                                                              |
| Tmax            | Represents the maximum time it took for a conversion event to occur for an ad channel                                                                                                                                                                             |

**Note**: All the above values can also be estimated at channel, objective, campaign, Ad group & Ad level