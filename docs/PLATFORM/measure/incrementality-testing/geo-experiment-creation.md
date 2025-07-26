---
title: Geo test creation
excerpt: Run experiments to determine your true marketing ROI & validate strategies
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Geo Experiments allow you to test changes in marketing strategies across geographic regions, helping to measure the impact on key performance metrics. Here's how to create one:

## View interactive demo

<br />

<Embed typeOfEmbed="iframe" url="https://lifesight.storylane.io/share/uwyisucnnpa9" html="false" iframe="true" href="https://lifesight.storylane.io/share/uwyisucnnpa9" height="600px" width="800px" />

<br />

<br />

## Steps to create a Geo test

1. Navigate to the Experiments page from the Nav bar on the left and click on the `Create Experiment` button.

<Image align="center" src="https://files.readme.io/b01b9ebfa991cd244af716405bba047c5d951decdbbdcefaa2e6973c2dc2e1f2-create_experiment.jpg" />

2. On the Set-up page, select “Geo Testing” under Experiment Type.
3. Select the Date range for the experiment, i.e., the date range from which you want to start the experiment and when it should end. An experiment can run for a minimum of 15 days.

<Image align="center" src="https://files.readme.io/31d8485aaf0a781da41dc774cd2bd925dfa0622e613c153b19c654548fada2dc-geo_setup.jpg" />

4. Upload the historical data in the form of a CSV file or choose Integrated method.
5. Map the schema by associating your input data with Lifesight's data types and input number of Geo's to experiment.

![](https://files.readme.io/f981c41215fd56824befb088666eb766df6ddf556f6abd62bcb367f1872486f0-image.png)

<br />

6. Name the experiment from the top-left of the setup page and click on `Next` to proceed.
7. On the campaigns, define your Test Cell. Select the platform and type of experiment (hold-out or scale-up). Input ‘Expected ROAS’ from the campaign.
   1. **Scale up tests** - Scaling up involves increasing the marketing budget in the test markets while keeping the budget the same in the control markets.
   2. **Holdout tests** - Holding Out involves exposing the test markets to a marketing activity/campaign while not exposing the control markets to the same marketing activity/campaign.
   3. **Expected ROAS** -

<Image align="center" src="https://files.readme.io/42571c723711f3c7e68fc7678dc6a490edd18143cef7808cde7e76916d726d93-GEO_CAMP.jpg" />

8. Click on ‘Add Cell’ to add more than 1 channel to test.
9. Click on 'Find 'Markets' to proceed.
10. After selecting your test campaigns, the status of the experiment will change to ‘**Finding Markets**’. The status will change to '**Markets Ready**’ once the test geos are identified. It usually takes 10–15 minutes for Lifesight to identify the test markets for the experiments.

<Image align="center" src="https://files.readme.io/3019d188381b2646c2e05c847ec51d28e0b65dd473c144e77dbd540d1b986ce1-MARKET_READ.jpg" />

<br />

11. Open the experiment with the status 'Market Ready'.
12. On the Markets page, select the test markets of each cell. View different treatment groups by current revenue share and budget required to run the test. Click on `Next` once you select a market.

<Image align="center" src="https://files.readme.io/ab4ac12fa175b25b79d4eb9029d61a3a375cbb057670a16718f8213186834684-TEST_MARK.jpg" />

12. Review the details of the experiment you want to start on the review page and click on `Save` to begin.

<Image align="center" src="https://files.readme.io/5bafa7bae1e171d6781aa08238a03791e06545d53b8c6615943c8a3e7b9d5213-GEO_REVIEW.jpg" />

> 🚧 Note
>
> **Data Table:** Create a table for each data set, including at least three key variables: time, location, and the measured Key Performance Indicator (KPI). Enhance accuracy by adding covariates.
>
> **Pre-Campaign Data:** Use historical data that is four to five times longer than the test duration. Minimum requirement: data from 25 pre-treatment periods across at least 20 geographical units.
>
> **Granularity:**
>
> * **Time:** Daily granularity.
> * **Geography:** Use the most detailed geographical unit available (city, state, zip) for precise insights.

<br />

### Lifesight creates a campaign on the target ad platforms (based on the cell-selected platform), with selected markets as holdouts or scale-ups for the suggested duration.

<br />

***

By following these steps, you can run an effective Geo Experiment to test marketing initiatives and optimize your strategy based on data-driven insights.