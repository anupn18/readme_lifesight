---
title: Split test creation
excerpt: Run experiments to determine your true marketing ROI & validate strategies
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Split Tests allow you to test the impact of marketing strategies on audience groups. This helps measure the lift in key performance metrics. Here's how to create one:

***

<br />

## Steps to create a Split Test

1. Navigate to the Experiments page from the Nav bar on the left and click on the `Create Experiment` button.

<Image align="center" src="https://files.readme.io/b01b9ebfa991cd244af716405bba047c5d951decdbbdcefaa2e6973c2dc2e1f2-create_experiment.jpg" />

2. On the Set-up page, select “Split Testing” under Experiment Type. 
3. Select the date range for the experiment, ie the from which you want to start the experiment and when it should end. It should be a minimum of 7 day period. There is also an option to end the experiment when statistical significance (95%) is achieved.

<Image align="center" src="https://files.readme.io/1327708fd0e04334ab6ada49ba487d9948430a2b3e7163a72fd229187314df45-split_test.jpg" />

4. Select the audience you want to experiment with. You can choose any existing segment or list from your workspace. The audience should be of at least 1000 contacts to experiment.
5. Select the Outcome/KPI whose lift you want to measure. You can measure the following metrics:
   1. Store Visits (count of page\_view, product\_view, product\_list\_view)
   2. Cart additions 
   3. Revenue 
   4. Number of orders
   5. Check-outs (count of checkout\_create)

<Image align="center" width="400px" src="https://files.readme.io/e6a942a8e84dd892d68470ab968658fc118ce723fb0e9f272d8c2dad1a5494de-image.png" />

6. Next, create the Splits for the experiment. With Splits, you can create randomized groups of users within your audience. You can specify:
   * **Control group** - Group of contacts that will not be exposed to any campaign.
   * **Treatment group** - Group of contacts who will be exposed to campaigns.\
     Mention the number of treatment groups you want to use and split percentage (for example, Control 10%, Treatment A 45%, Treatment B 45%)\
     Choose the destination to send each Treatment to; for example, Treatment A goes to Facebook and Treatment B goes to Google. The marketing channels that you have integrated with Lifesight will be available for selection. Contact from the Control group isn’t sent to any destination.\
     .

![](https://files.readme.io/aa50b1423706c595b327836a64210dc3e09b631695a75afda5f2f68c0619cc80-image.png)

<br />

6. Name the experiment from the top-left of the setup page and click on `Create Experiment` to complete creating a Split Test. Once the experiment is created, you can see it on the Experiments page. View the experiment based on the selected start time.
7. After this, open the treatment channel (*eg:Facebook ads, Google ads*) You will find the split test audience in your platform. 
8. Use the audience to run the experiment campaign on the respective channel for the mentioned experiment duration period.

> 📘 Important note
>
> 1. Custom segments will be synced to their respective platforms with null profiles when the experiment is created.
>
> 2. Ensure these audiences are applied to the necessary campaigns on their respective platforms from the scheduled start date of the experiment.
>
> 3. To avoid any unintended impacts on the experiment, we recommend applying the custom audience to all campaigns within an ad strategy or tactic.
>
> 4. Synced segments will be updated with profiles according to the specified split percentage on the experiment’s start date.
>
> 5. There would be only one control group.
>
> 6. Lifesight allows up to four treatment groups to be added as a Split.
>
> 7. All treatment groups would be of the same size.
>
> 8. Users can select auto-split, and the contact will be equally split among control and treatment groups. If auto-split is not selected, the user will have to input the percentage of the total audience membership to any of the treatment groups and control groups, and the rest of the percentage will be filled with criteria of equal treatment groups and remaining in the control group.
>
> 9. An ad platform can be selected multiple times as a destination.