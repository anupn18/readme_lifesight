---
title: View Through Attribution
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
View Through Attribution (VTA) in Lifesight helps you understand the impact of ad impressions that didn’t result in direct clicks but eventually led to a conversion. This method assigns credit to channels based on users who viewed ads but later converted through other means, such as direct or organic visits. Below is a high-level overview of how Lifesight calculates VTA.

### Fundamental Assumptions in Lifesight's View Through Attribution

1. Impact of Ad Impressions will eventually convert into Direct, Branded Search or Organic Search traffic into the website
2. As Lifesight has complete visibility into Website traffic , collected via Lifesight SDK, Lifesight could then use pattern between hourly deliver in impression and the corresponding spikes in web traffic to "spike" model for the impact of impressions on conversions
3. The Lag effect of impression to traffic is assumed to be under 24 hours

<br />

### Steps in Lifesight's View Through Attribution:

1. **Collecting Total Impressions by Channel**

   First, we gather total impressions for each channel from your ads data. This forms the foundation for understanding exposure across various platforms.
2. **Identifying Direct Visits and Click Proportions**

   Lifesight pulls data on direct visits (visits with no `utm_source`) and calculates the proportion of direct visits relative to the total clicks reported by integrated channels on a given date.
3. **Calculating Weights for Channels Impressions and Direct Visits**

   Lifesight applies the weight of direct derived wrt to clicks on the reported channels’ impressions to get corrected/reduced number of direct visits to be spared as baseline on any given date. This number is brought together with reported impressions to get new set of weights.
4. **Preparing Channel Affinity Data**

   For each customer journey, Lifesight prepares Channel Affinity data. This data is based on a visitor’s past journey through different marketing touchpoints. For example, if a user's journey was "Facebook → Google → Facebook," their affinity would be calculated as 0.66 for Facebook and 0.33 for Google.
5. **Assigning Impressions to Website Visitors**

   Lifesight assigns impressions to website visitors (including organic or direct) based on the calculated Channel Affinity scores and the weights from step 3. Both direct visits and channel impressions are assigned to ensure the baseline direct visits are respected.
6. **Handling Direct Visits in the Attribution Process**

   For visitors without a `utm_source` (direct visits), Lifesight assigns a weight based on their proportion in the overall visit pool. For example, if the direct visit weight is 0.1, then 10 out of 100 visitors (those with the least affinity toward integrated channels) would be left unassigned to any channel.

### Key Considerations:

- **Total Clicks**: These are derived solely from the ad channel reported data.
- **Direct Visits**: These are identified via `utm_source` tracking and play a role in balancing attribution.
- **Channel Affinity**: This is calculated for each visitor based on their historical interactions with various channels. This ensures that impressions are assigned logically, making sense for each unique visitor journey.

By combining these elements, Lifesight ensures a well-rounded view of how impressions from various channels might have contributed to visits/conversions, even when no direct clicks are involved.