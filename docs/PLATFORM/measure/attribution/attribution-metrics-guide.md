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

<HTMLBlock>{`
<table style="width: 100%; border-collapse: collapse;">
<thead>
<tr>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
</tr>
</thead>
<tbody>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Attributed Revenue</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>The total revenue generated from customer interactions that can be directly attributed to your marketing efforts.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>MER</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>MER (Marketing Efficiency Ratio) compares the total revenue generated to the marketing spend. A higher MER indicates more efficient marketing spend.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Attributed Revenue / Total Marketing Spends</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC Revenue </p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>(New Customer Revenue is the total revenue generated specifically from new customers acquired through your marketing efforts.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC ROAS</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>New Customer Return On Ad Spend is similar to ROAS, but focuses on the return on ad spend specifically for new customers acquired.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC Revenue / Ad Spend</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC MER</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>New Customer Marketing Efficiency Ratio is similar to MER, but focuses on the efficiency of marketing spend for acquiring new customers.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC Revenue / Ad Spend</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Att. Revenue Error</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Revenue Attribution Error Range represents the potential discrepancy in revenue attribution between platform-reported revenue and Lifesight&#39;s calculated revenue.<br>• Min Value: Indicating the minimum possible shortfall in revenue attribution.<br>• Max Value: Indicating the maximum possible over-attribution, accounting for direct traffic.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Min Value = platformRevenue - Attributed Revenue  </p>
<p>Max Value = (Direct + platformRevenue) - Attributed Revenue</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>NC AOV</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>New Customer Average Order Value is the average amount spent per order by new customers.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Ad Spend</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>The total amount of money you&#39;ve invested in marketing campaigns across all channels during the selected timeframe.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Impressions</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>The number of times your paid marketing message is displayed, regardless of whether a user clicks on it.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Platform Revenue</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Platform Orders</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
</tr>
</tbody>
</table>
`}</HTMLBlock>


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

<HTMLBlock>{`
<table style="width: 100%; border-collapse: collapse;">
<thead>
<tr>
  <th style="border: 1px solid #ddd; padding: 8px;">Metric name</th>
  <th style="border: 1px solid #ddd; padding: 8px;">Definitions</th>
  <th style="border: 1px solid #ddd; padding: 8px;">Formula</th>
</tr>
</thead>
<tbody>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Purchases</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Number of purchases events completed</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>New Purchases</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Number of new purchases events completed</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"></td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Cost Per Order</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Cost Per Order</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Ad spend / Order count</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>CAC</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Customer Acquisition Cost is the average cost of acquiring a new customer, considering all marketing and sales expenses.</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><ul>
<li></li>
</ul>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>LTV/CAC Ratio</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>The LTV/CAC ratio measures the efficiency of customer acquisition by comparing the lifetime value (LTV) of a customer to the cost of acquiring that customer (CAC).  </p>
<p>APV = Average Purchase Value = (total revenue / number of purchases) at the channel level<br>• APF = Average Purchase Frequency = (number of purchases / number of distinct customers) at the channel level<br>• CL = Customer Lifetime = The average duration from first purchase to last purchase across all customers in months</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>LTV = APV x APF x CL</p>
</td>
</tr>
</tbody>
</table>
`}</HTMLBlock>


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