---
title: Algorithmic Attribution
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Lifesight's Algorithmic Attribution

Algorithmic Attribution, often referred to as Data-Driven Attribution (DDA), is a modern and data-intensive approach to understanding the impact of various marketing touchpoints on conversions. Unlike rule-based models such as last-click or first-touch attribution, which apply rigid rules to credit specific touchpoints, DDA utilizes machine learning and statistical methods to dynamically assess the contribution of each interaction in a customer journey.

### Why is Algorithmic Attribution Needed?

1. **Considers Both Converting and Non-Converting Paths**\
   While traditional touch-based attribution techniques only give credit to touchpoints in converting paths, algorithmic attribution goes further by factoring in non-converting paths as well. This enables it to penalize touchpoints that appear frequently in journeys that do not lead to conversions, offering a more balanced and accurate view.

2. **Credit Based on True Contribution**\
   Algorithmic attribution assigns credit based on the true weight of a touchpoint in driving conversions, providing a more reliable representation of its role in the overall customer journey.

3. **Adjusts for Data Loss**\
   Data loss, which can occur due to factors like website bounces, user opt-outs from tracking, or ad blockers, is a common challenge in marketing attribution. Algorithmic attribution is capable of adjusting for such data loss, ensuring that your attribution model still reflects the broader trends in your marketing efforts.

4. **Complements View-Through Modeling**\
   Algorithmic attribution works alongside view-through modeling, enhancing the overall attribution process by integrating the impact of ad impressions that may not result in immediate clicks but contribute to conversions later in the journey.

***

### How Lifesight's Algorithmic Attribution Works

At Lifesight, we employ **Logistic Regression** to model attribution. This sophisticated statistical technique calculates the likelihood of a conversion based on the appearance and frequency of marketing touchpoints in a customer’s journey. 

#### Step-by-Step Process

1. **Data Aggregation**\
   Lifesight aggregates marketing touchpoints across all channels, including social media, search, and email, for each user interaction, whether they result in conversions or not. This data provides a complete view of customer journeys, both converting and non-converting, and is formatted for further model analysis.

2. **Logistic Regression Analysis**\
   The core of Lifesight’s algorithmic attribution lies in running a logistic regression, assigning weights to each marketing channel based on their influence on conversions. The model considers both conversion and non-conversion paths, offering a comprehensive analysis.

3. **Normalization of Weights**\
   Once the regression analysis is complete, the weights are normalized, meaning the total credit for each conversion adds up to 100%. This step provides an interpretable view of how each channel contributes to conversion, relative to others.

4. **Application of Weights to Attribution Reports**\
   The calculated weights are stored in Lifesight’s backend systems and reflected in the Multi-Touch Attribution (MTA) reports. These weights are updated when new data or channels become available, and they are applied to each marketing touchpoint, giving marketers granular insights into the effectiveness of their strategies.

***

### Other Important Points

1. **Setup Timeline**\
   Algorithmic Attribution is enabled within 14 to 30 days after your workspace setup, depending on the density of your data. If you do not see this feature activated in your Lifesight workspace, please reach out to the Lifesight support team for assistance.

2. **Refresh Cycle**\
   Algorithmic weights are refreshed on a monthly basis or upon user request, ensuring that your attribution model remains up to date with the latest marketing data.

***

### Summary

Lifesight’s Algorithmic Attribution provides a data-driven, precise method for understanding the real impact of your marketing touchpoints. With logistic regression, it delivers insights into both converting and non-converting paths, while adjusting for data loss and complementing view-through modeling. This empowers marketers to make data-backed, strategic decisions for continuous improvement and growth.
