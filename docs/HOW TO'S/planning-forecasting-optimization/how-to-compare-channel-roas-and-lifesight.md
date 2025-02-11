---
title: Lifesight ROAS vs platform ROAS
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## How We Calculate Lifesight ROAS vs. Platform ROAS

In this article, we’ll explain how Lifesight calculates Return on Ad Spend (ROAS) compared to the traditional platform ROAS. We will go step-by-step through the process, explaining key factors and providing a guide for new users who want to understand ROAS on our platform. 

### What is ROAS?

ROAS (Return on Ad Spend) is an important metric that tells you how much revenue you earn for each dollar you spend on advertising. There are two main ways ROAS is calculated:

- **Platform ROAS**: This is the ROAS calculated directly by advertising platforms like Google Ads or Facebook Ads. It uses platform-attributed revenue divided by the total spend on the platform.
- **Lifesight ROAS**: Calculated by tracking customer journeys with Lifesight’s SDK. Lifesight's ROAS gives you a more accurate view of revenue attribution by factoring in interactions across devices and touchpoints.

### How Platform ROAS is Calculated

The formula for platform ROAS is simple:

**Platform ROAS** = (Platform Attributed Revenue) / (Ad Spend)

Here, the revenue and spend data are obtained directly from the platform once you've integrated your ad channels (Google Ads, Facebook Ads, etc.) with Lifesight.

#### Example:

- Ad Spend: $1,000
- Revenue attributed by platform: $5,000
- **Platform ROAS** = $5,000 / $1,000 = 5.0

This means for every $1 spent, you earned $5 in revenue according to the platform.

### How Lifesight ROAS is Calculated

Lifesight ROAS uses more comprehensive data to give you a clearer picture of how your marketing efforts are performing. Here's how it works:

1. **Install the Lifesight SDK**: Once you install the Lifesight SDK on your website or app, it starts tracking all activities happening on your store, including visits, clicks, and conversions.

2. **Customer Journey Tracking**: Lifesight captures the complete customer journey using UTM parameters and other tracking mechanisms. This data is stitched together with the help of our **First-Party ID Graph**, which allows us to track users across devices and touchpoints.

3. **Attribution Model Selection**: Lifesight allows users to select an **Attribution Model** (such as first-click, last-click, or multi-touch attribution). This model decides how credit is divided among the various channels that contributed to the conversion.

4. **Assigning Revenue Credits**: Based on the selected Attribution Model, credits for each conversion are distributed across the channels involved in the customer’s journey. The credit share for every conversion is used to assign the corresponding revenue to each channel.

5. **Aggregating Channel-Level Revenue**: The revenue assigned to each channel based on the Attribution Model is aggregated to calculate the total **Lifesight-Attributed Revenue** for each channel.

#### Lifesight ROAS Formula:

**Lifesight ROAS** = (Lifesight-Attributed Revenue for the Channel) / (Spend for the Channel)

By using first-party data, Lifesight’s calculation provides a more holistic understanding of ROAS, incorporating cross-device tracking and multi-touch attribution.

#### Example:

- Ad Spend: $1,000
- Revenue attributed by Lifesight: $7,000
- **Lifesight ROAS** = $7,000 / $1,000 = 7.0

This means Lifesight shows that for every $1 spent, you're actually earning $7, offering a more comprehensive understanding of your marketing performance.

### Conclusion

Lifesight provides a deeper, more accurate understanding of ROAS by using first-party data and comprehensive attribution models. This allows you to see the true value of your marketing spend across channels and devices. By using both **Platform ROAS** and **Lifesight ROAS**, you can better optimize your marketing campaigns and improve your overall performance.