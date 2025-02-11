---
title: Overview
excerpt: Get a quick summary of your overall ad performance across multiple channels
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Overview Dashboard provides a quick summary of your ad performance across multiple channel. It encompasses both revenue and non-revenue metrics that are fundamental to your business operations.

<Image align="center" src="https://files.readme.io/8a0853cc6a1acbe2f0432806dcbefbce1f62a4c016c72bec4c09c5ec3edc019a-attribution.jpg" />

## The Overview tab contains the following sections:

1. Attribution status
2. Target Benchmark KPI
3. Metrics Summary
4. Attribution Chart 
5. Channel Breakdown

## View interactive demo

<Image alt="[Click here](https://lifesight.storylane.io/share/zlwdx65j8qhf) to view demo in fullscreen" align="center" src="https://files.readme.io/94991ede25dd051980b388615e66f144dc327b57799a4c0595c30fb7e6bdbb50-image.png">
  [Click here](https://lifesight.storylane.io/share/zlwdx65j8qhf) to view demo in fullscreen
</Image>

<br />

***

## Key Components

### Attribution status

The status indicators help understand when was the last Platform data and Attribution data synced to your Lifesight Attribution dashboard.

* **Platform data** - Hover over the platform data to view when was the last time each of your ad channels had a data sync. Incase there any integration with a ad channel is broken, users would be able to see a last time stamp when the data was synced.
* **Attribution data** - Hover over the platform data to view when was the last time each of your attribution data was synced. If you make changes to Rules and Labelling, the Attribution data would need to refresh based on the mentioned rules and would show the latest timestamp of the data sync. While data is updating you would see a "Processing" status marked in the Attribution dashboard.

<Image align="center" src="https://files.readme.io/69db8f7a07adb5b6fb7d3890749b07f12987e870043daf863990922a02cf0d89-status.jpg" />

### Target Benchmark KPI

Target Benchmarks are useful when a business wants to input their Target KPI and optimize their marketing efforts to achieve the goal. Click to learn more about [Target Benchmark](https://docs.lifesight.io/docs/how-to-use-target-benchmark-in-attribution)

<Image align="center" src="https://files.readme.io/7d7ff15815e54220965eb4e27068e44a62aada43aef01ec5f88e8f6be87f9af7-target.jpg" />

### Attribution period

Select a date range to apply to your attribution reports. By default, the data is showcased for the previous seven days. 

### Attribution Model

Choose between different Attribution models such as Last Touch, First Touch, Multi-Touch (Linear), U-Shaped, Time Decay, Algorithmic, and Causal.

<Image align="center" width="200px" src="https://files.readme.io/b2a835548425678c3632b0c05aed8c2bb3940aed122972ae304ef0a8d2ab5fbd-image.png" />

> 📘 Algorithmic model
>
> We enable algorithmic model 14 days after integrating all your data sources. Lifesight runs an algorithm independently to give credits to various touch points for the algorithmic model. We give credit to all the touch points in converting paths. But at the same time, we would penalize all the touch points in non converting paths.

> 👍 How does Causal model work?
>
> Causal model works when you select a [Default Scenario](https://docs.lifesight.io/docs/default-scenario). Hover over the info help indicator to view which models the causal attribution model is based on. You can have multiple default scenarios and the causal model autopicks the best plans for a KPI to calibrate platform attribution reports with the MMM incrementality factor.

### Attribution window

An attribution window is the number of days between when a person viewed or clicked your ad and subsequently took action.

![](https://files.readme.io/5f3f87827d8644f9e419b12d391cec654520871c1315fe53b7928d0061af82d6-image.png)

### Attribution Method

We measure ad actions based on clicks and views of your ad:

* **Click-through attribution:** A person clicked your ad and took an action.
* **View-through attribution:** A person saw your ad, didn't click it, but took an action within the attribution window.

Read more on how View-Through Attribution works (coming soon)

![](https://files.readme.io/78b4e629539cab849a99e5fa8fb77ae032edc5dfe5cd39a738187b8d490d6fa2-image.png)

<br />

## Summary of Key Metrics

The Overview dashboard displays the metrics you select by aggregating the touchpoint data, cost data, and event data from various sources. 

![](https://files.readme.io/3f56bd3b810df0eeebf0ac330ef2a3efd1537303fedbeab3208f5aef64b25ee5-image.png)

**The metrics are categorized as:**

1. Revenue and Efficiency - Att. Revenue, ROAS, MER, NC Revenue, NC ROAS, NC MER, Att. Revenue Error
2. Cost and Spend - Cost Per Order, CAC, CPA (Visits), CPA (Add to Cart), CPA (Signups), LTV/CAC
3. Customer Behavior - AOV, NC AOV, Signups, Add to Cart, Visits
4. Advertising - Ad Spend, Impressions, Platform Revenue, Platform Orders
5. Non-Revenue KPIs - pOrders, pRegistrations, pAddtoCart, pLeads, pRevenue (existing)

> 📘 Incremental metrics are shown only for Causal Attribution models

> 👍 Attribution Error range (only shown for Causal Attribution models)
>
> This metrics highlights the potential discrepancies between platform-reported revenue and Lifesight's calculated revenue. 
>
> <Image align="center" src="https://files.readme.io/41fd47c46888607e9d2e6734f7d43f1fb37b1f810d43ca1e90ea6fc70d8b0c39-image_1.png" />
>
> **Key Details:**
>
> * **Min Value**: Represents the minimum possible shortfall in revenue attribution. Calculated as the difference between `platformRevenue` and `Attributed Revenue`.
> * **Max Value**: Represents the maximum potential over-attribution, calculated as `(Direct Traffic + platformRevenue) - Attributed Revenue`.
>
> This feature is designed to help users better understand the accuracy of platform-reported revenue figures, providing insights into the extent of revenue attribution errors.

Click here to get a detailed explanation in the [Attribution metrics guide]().

> 🤔 How are metrics calculated?
>
> Hover over each metric name to view the definition and formula used to calculate the metric values. 
>
> <Image align="center" width="300px" src="https://files.readme.io/0ae1842f6ccc93cbbb8296a0487c57463a7c3393efadaea54c81562280e0a4e9-image.png" />

<br />

## Attribution chart

This powerful chart lets users compare metrics across dimensions, time period and channels to uncover hidden patterns and opportunities.

<br />

Easily switch between line and bar charts for a fresh perspective on your data, helping you quickly spot trends and insights. Export your charts and data in formats like PNG, JPG, PDF, SVG, CSV, and XLSX for seamless integration into presentations and reports. Align chart axes for accurate, scale-to-scale comparisons, ensuring more precise and meaningful data analysis.

Learn more about Attribution charting

![](https://files.readme.io/2c2bc29e6ef1d349d573131c4a22692b1cf54bc147e897f52d736461b1088bc1-image.png)

<br />

## Channel Breakdown

The Channel Breakdown chart provides a comprehensive view of ad channel performance at a granular level, allowing for drill-down analysis into smaller, more specific subsets. 

![](https://files.readme.io/ae92dc3a10164ac5c26311f14328e2a729001ad2cb7fa284d1edcb67ec262818-image.png)

By delivering actionable insights through Recommendations like "Scale up" or "Stop," the tool helps optimize marketing efforts based on your Target Benchmark metrics set in the Attribution dashboard. Click here to learn on [Target Benchmarks]()

The channel performance is analyzed across the following levels:

* Channel, Campaign, Objectives, Ad Groups, Ads

Performance metrics are organized into the following categories:

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Metric category
      </th>

      <th style={{ textAlign: "left" }}>
        Metric
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Engagement
      </td>

      <td style={{ textAlign: "left" }}>
        Clicks\
        Impressions
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Conversions
      </td>

      <td style={{ textAlign: "left" }}>
        Visits\
        CPA(Visits)\
        Signups\
        CPA( Signups)\
        Form Submits\
        CPA (Form Submits)\
        Add to Carts\
        CPA (Add to Carts)\
        pOrder\
        pCPA
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Revenue
      </td>

      <td style={{ textAlign: "left" }}>
        AOV\
        pRevenue\
        UTM Revenue (As captured by pixel + attribution methodology selected in the filters)\
        Channel vs UTM\
        UTM New Revenue
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Purchases
      </td>

      <td style={{ textAlign: "left" }}>
        Purchases\
        New Purchases\
        CPO\
        CAC\
        LTV/CAC
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Spend
      </td>

      <td style={{ textAlign: "left" }}>
        Spend
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        ROAS (Return on Ad Spend)
      </td>

      <td style={{ textAlign: "left" }}>
        pROAS\
        UTM ROAS (As captured by pixel + attribution methodology selected in the filters)\
        UTM NC ROAS (As captured by pixel + attribution methodology selected in the filters)
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Time to Convert
      </td>

      <td style={{ textAlign: "left" }}>
        Conversion rate\
        Average\
        25th Percentile\
        50th Percentile\
        75th Percentile\
        Tmax
      </td>
    </tr>
  </tbody>
</Table>

### [View all Attribution metric definitions](https://docs.lifesight.io/docs/attribution-metrics-guide)

> 📘 Note
>
> The "Settings" icon in Name section of the table helps filter the metrics you want to view in your Channel Breakdown table. 
>
> <Image align="center" width="400px" src="https://files.readme.io/f407242c1c0eed8ab5a851b1b7387ee78106f9f857466c9a21a17b1e337c9855-image.png" />
