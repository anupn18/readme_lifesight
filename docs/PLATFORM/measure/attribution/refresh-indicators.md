---
title: '[WIP] Refresh Indicator'
deprecated: false
hidden: true
metadata:
  robots: index
---
To ensure you are making decisions with the most up-to-date information, the Lifesight platform provides clear data freshness indicators. These indicators tell you the status of your data at two critical stages: when it's ingested from your marketing platforms and when it's processed by our attribution models.

<br />

### Locating the Refresh Indicators

You can find both refresh indicators located in the top-right corner of the **Attribution** pages, next to the forecast dropdown menu.

![Location of the Platform and Attribution data refresh indicators](Screenshot%202025-09-02%20at%2012.39.54%E2%80%AFPM.jpg)

***

### Platform Data Indicator

The **Platform Data** indicator monitors the real-time ingestion of data from all your connected sources, such as Google Ads, Facebook Ads, and LinkedIn Ads. Its primary purpose is to confirm that Lifesight is successfully pulling the latest performance data from your marketing platforms.

When all integrations are functioning correctly, the status will show as **Refreshing**.

By hovering your mouse over this indicator, a tooltip will appear, showing a detailed breakdown of each connected platform and the timestamp of its last successful data sync.

> [!NOTE]
> The timestamp reflects the last moment Lifesight successfully fetched new data from the source platform. It is a direct indicator of the health of that specific integration.

***

### Attribution Data Indicator

The **Attribution Data** indicator shows the last time the core attribution models were successfully run using the ingested platform data. This process synthesizes all the raw data into the final attributed metrics you see across the platform.

> [!WARNING]
> The attribution modeling process runs **once per day**. The timestamp on this indicator will update daily to reflect the latest completed model run.

The data refreshed during this daily process includes:

* Journeys
* Purchases
* Conversions

***

### Common Scenarios

**What should I do if an integration's timestamp under "Platform Data" is not recent?**

If you notice a timestamp for a specific platform is more than a few hours old, it may indicate an issue with the data sync for that integration. We recommend navigating