---
title: Geo test insights
excerpt: Learn how to analyze your Geo Test results and use it for MMM calibration
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Open the Geo Test whose experiment status is marked as "**Completed**".

<Image align="center" src="https://files.readme.io/d08c66ab30361c70e1c00f38e39a569796d17ccb667d7affe8a3004692d91e05-geo_results.jpg" />

The time-value graph shows the KPI trend for the Control group against the selected Treatment group. Select the drop-down menu at the top right to switch between different treatment groups.

The Results table shows the following details:

* **Group name** - Shows the Treatment group and the match markets involved in the test.
* **Platform** - Shows the destination platform in which the experiment was run.
* **Treatment** - Shows the type of experiment run (Scale-up or Holdout test)
* **KPI** - Shows the outcome KPI the experiment was measured for (Revenue, Orders, Store Lift, etc)
* **Statistical Significance** - Indicates whether the experiment's results are likely due to the treatment effect rather than chance, confirming the reliability of the outcome. Generally, the higher the better.
* **KPI Lift** - Shows KPI lift due to the experiment for each treatment group.
* **Lift** - Percentage lift in KPI by running the experiment for each treatment group.

<br />

## Calibrating MMM model with Geo Test results

Now that you've run an Experiment successfully and the results make sense to you as a marketer. You can input these results to your MMM model and calibrate them to improve the model accuracy. Follow the steps to calibrate your model:

1. Open a MMM model from the Measure > MMM from the navbar.
2. Select `Reconfigure` button from the top right of the MMM dashboard.

   ![](https://files.readme.io/b26600beb328912a4a2416e6967bd41b703c14a5bb613a5db7fc6878940009de-image.png)
3. Name your new model and click `Continue`.
4. Click `next`in the Features step and go to Conguration step.
5. Scroll to the bottom of the Configuration page to view the Calibration table.
6. Enter the results of your Experiment here and click the `Re-configure` button to confirm your changes.

<Image align="center" src="https://files.readme.io/81472ddd76dab98659c6d7b7c752ce8073b26973ddf79695c197878963fa65ec-calibration.jpg" />

7. A new model with the recalibrated changes will be created with the refresh version number mentioned in the model name.

![](https://files.readme.io/1cf072f1b2d24e9510d6520d8c09728c2176bb74a9316c89af89c4c584de590a-image.png)

> 📘 Note
>
> Whenever a model is refreshed or calibrated, a new model is created. This is done in case you added the incorrect experiment results or ran a failed experiment whose results you are not happy with. Users can deleted the refreshed model and seamlessly return to their main model without having the create a new model from scratch.
