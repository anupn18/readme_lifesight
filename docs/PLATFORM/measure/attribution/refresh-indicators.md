---
title: '[WIP] Refresh Indicators'
deprecated: false
hidden: true
metadata:
  robots: index
---
The Attribution dashboard features two key indicators to verify your data's freshness: **Platform Data** and **Attribution Data**.

* **Platform Data** confirms that data is being actively synced from your marketing channels.
* **Attribution Data** shows the last time this synced data was processed by our models.

This guide breaks down how to interpret each indicator to ensure your data is current.

<br />

### Locating the Refresh Indicators

You can find both refresh indicators located in the top-right corner of the **Attribution** pages, next to the Target Benchmark button. 

<Image align="center" alt="Location of the Platform and Attribution data refresh indicators" src="https://files.readme.io/e1ee244dca1b62cd44d0b756ca82933f60c9e0704f36c09230db4e166e969662-Refresh_Indicators.png" />

***

### Platform Data Indicator

The **Platform Data** indicator monitors the real-time ingestion of data from all your connected sources. Its primary purpose is to confirm that Lifesight is successfully pulling the latest campaign data from your marketing platforms.

When all integrations are functioning correctly, the status will show as **Refreshing**.

By hovering your mouse over this indicator, a tooltip will appear, showing a detailed breakdown of each connected platform and the timestamp of its last successful data sync.

<Image align="center" src="https://files.readme.io/61345673b2e4ff7164b5940943d5ad31f97812883133645908c348043a68eaa7-Screenshot_2025-09-02_at_12.39.54_PM.png" />

<Callout icon="👍">

  The timestamp reflects the last moment data was successfully fetched from the source platform. It is a direct indicator of the health of that specific integration.
</Callout>

***

### Attribution Data Indicator

The **Attribution Data** indicator shows the last time the core attribution models were successfully run using the ingested platform data. This process synthesizes all the raw data into the final attributed metrics you see across the platform.

> [!WARNING]
> The attribution modeling process runs **once per day**. The timestamp on this indicator will update daily to reflect the latest completed model run.

***

### Common Scenarios

**What should I do if an integration's timestamp under "Platform Data" is not recent?**

If you notice a timestamp for a specific platform is more than a few hours old, it may indicate an issue with the data sync for that integration. We recommend navigating
