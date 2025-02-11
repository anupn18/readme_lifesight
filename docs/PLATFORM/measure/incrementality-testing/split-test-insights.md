---
title: Split test insights
excerpt: Learn how to analyze your Split Test results and use it for MMM calibration
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
You can view insights for both ongoing and completed experiments on the Experiments page. To see results for a specific experiment, select it from the list.

The time-value graph shows the total number of events performed by customers in each group over time, along with performance data. Use the drop-down menu at the top right to switch between 'Total' (cumulative results for both treatment and control groups) and 'Uplift' (the difference between the treatment group and normalized control group).

For an apples-to-apples comparison, toggle 'Show normalized control' to scale the control group’s revenue to match the treatment group’s size. The table below provides a detailed summary of results.

![](https://files.readme.io/1f352993e7e892788b4b27ab1c380ed2605842bd79c2031076724d2a49841274-image.png)

Here's what you can infer from the above Split Test to measure Store Visit Lift.

- Snapchat had a negative Lift of 6.93% which resulted in 432 fewer Store Lifts after being exposed to the campaign.
- Pinterest had a negative Lift of 14.62% which resulted in 912 fewer Store Lifts after being exposed to the campaign.

<br />

## Calibrating MMM model with Split Test results

Now that you've run an Experiment successfully and the results make sense to you as a marketer. You can input these results to your MMM model and calibrate them to improve the model accuracy. Follow the steps to calibrate your model:

1. Open a MMM model from the Measure > MMM from the navbar.
2. Select `Reconfigure` button from the top right of the MMM dashboard.

   ![](https://files.readme.io/b26600beb328912a4a2416e6967bd41b703c14a5bb613a5db7fc6878940009de-image.png)
3. Name your new model and click `Continue`.
4. Click `next`in the Features step and go to Conguration step.
5. Scroll to the bottom of the Configuration page to view the Calibration table.
6. Enter the results of your Experiment here and click the `Re-configure` button to confirm your changes.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/81472ddd76dab98659c6d7b7c752ce8073b26973ddf79695c197878963fa65ec-calibration.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


7. A new model with the recalibrated changes will be created with the refresh version number mentioned in the model name.

![](https://files.readme.io/1cf072f1b2d24e9510d6520d8c09728c2176bb74a9316c89af89c4c584de590a-image.png)

> 📘 Note
> 
> Whenever a model is refreshed or calibrated, a new model is created. This is done in case you added the incorrect experiment results or ran a failed experiment whose results you are not happy with. Users can deleted the refreshed model and seamlessly return to their main model without having the create a new model from scratch.