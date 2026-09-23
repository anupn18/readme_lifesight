---
title: Custom Budget Pacing
excerpt: Align your monthly spend with seasonality, promotions, and media commitments.
deprecated: false
hidden: false
metadata:
  title: Custom Budget Pacing
  description: >-
    Align your monthly spend with seasonality, promotions, and media
    commitments.
  keywords:
    - Lifesight Custom Budget Pacing
  robots: noindex
---
Custom budget pacing lets you control how your planned budget is spread across each month of your plan period, instead of splitting it evenly. You can set a budget for each month and apply month-specific channel constraints (spend limits per channel), so your scenario forecasts results based on when you actually plan to spend.

![](https://files.readme.io/20a564e787df0002e1a8264ac5bf65d8789a64b644d96806547967d938662852-Screenshot_2026-09-21_at_2.13.33_PM.png)

<br />

\[IMAGE PLACEHOLDER: Advanced Configuration Custom Pacing tab]

## Know when custom pacing will improve your plan

Use custom pacing when your spend should not be spread evenly across the plan period. Common reasons include:

- **Seasonality:** increasing spend ahead of peak demand periods, such as holidays or back-to-school.
- **Launches:** concentrating budget around a new product or campaign launch.
- **Promotions:** supporting sales events or limited-time offers with heavier spend.
- **Inventory limits:** pulling back spend when stock is limited, so you don't drive demand you can't fulfill.
- **Contractual media commitments:** reflecting spend agreed with media partners for specific months.

Pacing your budget this way gives you a more realistic forecast, since Planner models results based on when spend actually happens.

## Set up custom pacing for your scenario

1. Open a Planner scenario.
2. &#x20;If you select plan period as 1 month in configuration custom pacing wont appear. To edit the custom pacing setting ensure to select the plan period more than 1 month. Then select **Advanced Config**.

   ![](https://files.readme.io/11d8261cd21970a5d7506dc24845f920ad614eb7db6f1cfd5d6558c5f9ffd383-Screenshot_2026-09-21_at_2.27.29_PM.png)


3. Open **Custom Pacin tab**.

   ![](https://files.readme.io/cac1a57a03b310a7de3fbf881a048ac84e5f36ae8d5b460735f5c3d7746da3a3-Screenshot_2026-09-21_at_2.29.38_PM.png)
4. Review the current and planned budget for each month. Current budget reflects spend from your reference period (the past window used as your baseline).

   ![](https://files.readme.io/2e1ef5decadbf4dcb4bad950f8bac742353c3b055b0088810312dc800561cfcb-Screenshot_2026-09-21_at_2.30.05_PM.png)
5. Edit monthly budgets directly, or upload a pacing plan.
6. Review channel constraints for each month and adjust them where needed.

   ![](https://files.readme.io/7739b0928fe67c270048c116c1be647bb466d489336e1671e77ab0326cc6ddd8-Screenshot_2026-09-21_at_2.33.19_PM.png)
7. Confirm that your monthly budgets add up to the total planned budget.
8. Select **Apply** or **Done**, then run the simulation to see your updated forecast.

## Understand how Planner fills in the months you don't edit

You don't need to set a budget for every month. Planner distributes the remaining budget across any months you leave unchanged:

- **If current monthly spend is available,** Planner divides the remaining planned budget across unmodified months in proportion to that spend, so your existing seasonal patterns carry forward.
- **If current monthly spend is not available,** Planner divides the remaining budget evenly across unmodified months.
- **The final unmodified month absorbs any rounding,** so your monthly budgets always add up exactly to the total planned budget.

Channel bounds are also set month by month. Each month's channel limits are scaled from that month's planned budget and applied as constraints for that period, so a lighter month gets proportionally smaller channel limits and a heavier month gets larger ones.

## Make sure your pacing plan is valid

Before you can apply custom pacing, your plan needs to meet a few rules:

- Every monthly budget must be greater than zero.
- Monthly budgets must stay within allowed limits.
- All monthly budgets must add up to the total planned budget.
- Channel minimums cannot be negative.
- Channel minimums cannot be higher than their maximums.

If these are not met you might face errors such as appearing in the image below like `Monthly budgets don't add up to the total planned budget — adjust a month before continuing. `

Each month has its own tab at the top of Custom Pacing (for example, Sep 26 and Oct 26), and each month has its own planned budget. The channel budgets you set within a month cannot add up to more than that month's planned budget.

For example, if Sep 26 has a planned budget of $1,000,000 and your channel budgets for September add up to $1,200,000, Planner shows an error because you've assigned $200,000 more than the month allows. Reduce one or more channel budgets until the total is $1,000,000 or less, then repeat the check for each month.

![](https://files.readme.io/a5518d116f48e95f954af4c4d44cb5d248be3fec59a47e964560173b1a4a6f2f-Screenshot_2026-09-21_at_2.47.45_PM.png)

Also,if you are uploading a pacing plan, start from the provided template and keep the CSV file under the file-size limit shown in the platform. Using the template makes sure your file is in the right format to upload.

![](https://files.readme.io/3bf58373c7d25916bb308ee29eb130ff83ea5fda3729a91b7405c90d4364c915-Screenshot_2026-09-21_at_3.00.32_PM.png)

If you are not able to edit the variable constraints ensure you have selected the manaual option from the dropdown on the right.

![](https://files.readme.io/b3314d6a0e392eeeaf023d86e61b5527a98288d36713af97ec048f0ebc12e32e-Screenshot_2026-09-21_at_2.59.09_PM.png)

***

## Frequently asked questions about custom budget pacing<br />

### What is custom budget pacing in Lifesight?

Custom budget pacing lets you distribute a scenario's planned budget across individual months instead of evenly across the plan period. You can also apply month-specific channel constraints, so Planner forecasts results based on when you actually plan to spend.

### When should I use custom pacing?

Use custom pacing when your spend should not be spread evenly. Common reasons include seasonality, product launches, promotions, inventory limits, and contractual media commitments.

### How do I set up custom pacing in Planner?

Open a Planner scenario with a plan period longer than one month, select **Advanced Config**, and open **Custom Pacing**. Review the current and planned budget by month, then edit monthly budgets or upload a pacing plan. Review channel constraints for each month, confirm the monthly totals match your planned budget, select **Apply** or **Done**, and run the simulation.

### Why can't I see Custom Pacing in Advanced Config?

Custom pacing is only available when your plan period is longer than one month. If your plan period is set to one month, update it to two months or more in your scenario configuration, then open **Advanced Config** again.

### Do I need to set a budget for every month?

No. Planner distributes the remaining budget across months you leave unchanged. It uses current monthly spend to split the remainder when that data is available, and divides it evenly when it is not.

### What happens to rounding differences in monthly budgets?

The final unmodified month absorbs any rounding, so your monthly budgets always add up exactly to the total planned budget.

### How are channel constraints applied with custom pacing?

Each month has its own tab in **Custom Pacing**, such as **Sep 26** and **Oct 26**, with its own planned budget. Each month's channel limits are scaled from that month's planned budget and applied as constraints for that period. Months with larger budgets get proportionally larger channel limits.

### Why can't I edit the variable constraints?

Make sure **Manual** is selected in the dropdown on the right of **Variable Constraints**. Once Manual is selected, you can set your own minimum and maximum spend limits for each channel.

### Why am I seeing an error when I apply custom pacing?

Errors appear when your pacing plan doesn't meet the validation rules. A common one is "Monthly budgets don't add up to the total planned budget," which means you need to adjust a month before continuing. Errors also appear when the channel budgets within a month add up to more than that month's planned budget.

### What happens if my channel budgets add up to more than the month's planned budget?

Planner shows an error. For example, if **Sep 26** has a planned budget of $1,000,000 and your channel budgets for September add up to $1,200,000, you've assigned $200,000 more than the month allows. Reduce one or more channel budgets until the total is $1,000,000 or less, then check each remaining month.

### Why can't I apply my custom pacing plan?

Your pacing plan must meet validation rules before it can be applied. Every monthly budget must be greater than zero, stay within allowed limits, and add up to the total planned budget. Channel budgets within a month cannot exceed that month's planned budget, and channel minimums cannot be negative or higher than their maximums.

### Can I upload a pacing plan instead of editing months manually?

Yes. Select **Template** in **Custom Pacing** to download the template, fill in your monthly budgets, and select **Upload Plan** to upload it as a CSV file.

### Is there a file-size limit for uploading a pacing plan?

Yes. Keep your CSV file under the file-size limit shown in the platform. Starting from the provided template also makes sure your file is in the right format to upload.

### Do I need to rerun the simulation after changing pacing?

Yes. After selecting **Apply** or **Done**, run the simulation so your forecast and recommendations reflect the new monthly pacing.

***

## Related Articles

<Cards>
  <Card title="Set a default scenario" icon="fa-rocket">

  </Card>

  <Card title="Interpreting a Plan" icon="fa-code">

  </Card>
</Cards>