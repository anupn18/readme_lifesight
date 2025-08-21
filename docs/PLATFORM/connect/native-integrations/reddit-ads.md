---
title: Reddit Ads
deprecated: false
hidden: false
metadata:
  robots: index
---
The Reddit Ads API allows advertisers to programmatically tap into the Reddit Ads Platform to extract advertising campaign and account data. By integrating the Reddit Ads API with Lifesight, you can reduce operational overhead and accelerate the reporting of Reddit campaigns without needing to step into the Reddit Ads Manager directly.

<br />

This integration empowers you to unify granular Reddit Ads performance data with your broader marketing and business datasets within the Lifesight Unified Marketing Measurement (UMM) platform.

<br />

### **Primary Use Cases: MMM and Causal Attribution**

<br />

Connecting your Reddit Ads account unlocks powerful, advanced measurement capabilities within Lifesight.

* **Marketing Mix Modeling (MMM):** To accurately measure the true impact of your Reddit advertising, Lifesight ingests granular, multilevel data. This rich dataset is essential for our MMM engine to precisely model Reddit's contribution to your overall marketing mix and its effect on key business outcomes.
* **Causal Attribution:** The insights generated from the MMM are then used to perform causal attribution. This allows you to understand the effectiveness of your Reddit Ads at various hierarchies, from the overall account level down to specific campaigns, ad groups, and individual ads, and optimize your strategy accordingly.
  <br />

### **Data Ingestion from Reddit Ads**

<br />

Lifesight pulls comprehensive data from all available hierarchies within the Reddit Ads platform to ensure your models are robust and your insights are detailed.

<br />

The standard advertising structure in Reddit includes the following levels, and Lifesight ingests data from each:

* **Campaigns:** The highest level where you set a primary objective.
* **Ad Groups:** Where you define targeting, budget, and scheduling.
* **Ads:** The individual creative units shown to users.

  <br />

Key **metrics** and **dimensions** brought into Lifesight include:

| Category                 | Data Points                                                         |
| :----------------------- | :------------------------------------------------------------------ |
| **Performance Metrics**  | Spend, Impressions, Clicks, Click Through Rate (CTR), Video Views.  |
| **Conversion Metrics**   | Sign ups, Add to Carts, Purchases, Page Visits, Custom Conversions. |
| **Cost Metrics**         | Cost Per Click (CPC), Cost Per Mille (CPM).                         |
| **Hierarchy Dimensions** | Campaign Name, Ad Group Name, Ad ID, Ad Name.                       |

<br />

### **Steps to Integrate Reddit Ads**

Connecting your Reddit Ads account is a straightforward, single authentication process.

1. Navigate to the **Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**Reddit Ads**" to locate the integration tile.
3. Click on the **Reddit Ads** tile and then click the **Next** button.
4. You will be redirected to a Reddit authentication screen. Log in using your Reddit Ads account credentials.
5. Review the permissions screen, which details the data Lifesight will access, and click **Allow**.
6. Upon successful authentication, you will be returned to the Lifesight platform.
7. From the list provided, select one or more ad account IDs from which you want to pull data.
8. Click **Finish** to complete the setup. Your selected accounts will now be connected.

<br />

Once the integration is complete, Lifesight will begin the initial data pull from your selected Reddit Ads accounts. This process may take some time depending on the volume of your historical data.