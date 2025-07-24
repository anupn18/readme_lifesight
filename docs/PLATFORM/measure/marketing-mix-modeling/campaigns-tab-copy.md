---
title: Campaigns tab (COPY)
excerpt: Giving campaign level insights using Triangulation Methodology
deprecated: false
hidden: false
metadata:
  robots: index
---
Gain granular strategic campaign-level insights based on incrementality using MMM - enabling media buyers to accurately assess the effectiveness of each campaign and make calculated decisions.

<Image align="center" src="https://files.readme.io/b1d2077418aaf0f118816fc15dbc6578d7e70f07704d73bc26c6e610d9feb7c7-campaigns.jpg" />

***

Provide users with a clear view of the ROAS for each campaign to support informed decisions about marketing budget allocation. Use triangulation to enhance attribution accuracy by integrating insights from multiple data sources, offering a more reliable assessment of marketing impact.

The main concept that we are using in the campaign insights tab is using the `Attribution and MMM` numbers to calculate for `incrementality` factor .

* We calculate the incrementality factor using the Platform Return on Ad Spend (pROAS) and the Incremental Return on Ad Spend (iROAS), where iROAS is derived from Marketing Mix Modeling (MMM).
* Merge MMM Insights with Ad Insights and compile a list of campaigns, including pROAS, pRevenue, and we adjust these metrics using the `Incrementality` Factor.

## Data Fields

The table below lists all the key fields involved in the process:

* **Campaign**: The name of the campaign.
* **Tactic**: The specific tactic used within the campaign.
* **Impressions**: The number of impressions as reported by the platform.
* **Clicks**: The number of clicks as reported by the platform.
* **Spend**: The total spend as reported by the platform.
* **pRevenue**: Platform-reported revenue OR **pConversions**: Platform-reported conversions.
* **iRevenue**: Incremental revenue OR **iConversions**: Incremental conversions, calculated using MMM. 
  * Formula: `iRevenue = pRevenue * Incrementality Factor`
* **pROAS**: Platform Return on Ad Spend OR **pCPA**: Platform Cost Per Action, as reported by the channel.
* **iROAS**: Incremental ROAS OR **iCPA**: Incremental Cost Per Action, calculated using MMM. 
  * Formula: `iROAS = iRevenue / Spend`
* **Contribution**: The percentage contribution to overall revenue or conversions.