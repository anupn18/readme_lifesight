---
title: '[4.0][Updated] CSV Data Formatting Guidelines'
excerpt: Prepare CSV data for Marketing Mix Modeling in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
High-quality input data is the foundation of an accurate and actionable Marketing Mix Model. In Lifesight, you can create a model from an existing Data Model or upload a CSV file and map every field manually.

### CSV Template

Use the sample template as a starting point for your file.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1915444742#gid=1915442">View MMM CSV Sample Template</Anchor>

![](https://files.readme.io/495df6dae631bc6e37ecde802ef91c5e2ffff4ae42ae7ef0b64aa5ad8cdf6dd7-Screenshot_2026-09-11_at_3.52.34_PM.png)

## Data Requirements

Your CSV must contain the fields required to define the model's outcome, paid media, and time window.

### Mandatory Columns

* **Date Column:** A date field in `YYYY-MM-DD` format.
* **KPI Column:** At least one outcome you want to model, such as `Revenue`, `Orders`, `Installs`, or `New_Customers`.
* **Paid Media Spend:** At least one numeric spend field for a paid channel or tactic.

The variable mapper requires a channel and spend field for every paid row. Tactic, impressions, and clicks are optional.

### Recommended Additional Columns

| Category       | Recommended variables                                                                    |
| :------------- | :--------------------------------------------------------------------------------------- |
| **Paid Media** | Spend, impressions, and clicks at the channel or tactic level                            |
| **Organic**    | Organic sessions, direct traffic, email activity, or other owned and earned signals      |
| **Contextual** | Promotions, pricing changes, holidays, weather, competitor activity, or macro indicators |
| **Halo**       | Cross-channel or cross-product variables used to represent spillover effects             |
| **Dimensions** | Country, region, product, or another field used to fit dimensional child models          |

For organic, contextual, and halo variables, you will select a Positive, Negative, or Neutral impact during model creation.

## Formatting and Validation Checklist

<Callout icon="🚧" theme="warn">
  ### Review the file before uploading it. A clean header row and consistent time series make mapping and validation much easier.
</Callout>

### File and Header Rules

* [ ] Save the file as CSV. The upload control accepts CSV files up to 50 MB.
* [ ] Include one header row.
* [ ] Use unique, descriptive column names.
* [ ] Remove blank rows and blank columns.
* [ ] Avoid columns that contain only zeros.

### Date and Time Rules

* [ ] Format every date as `YYYY-MM-DD`.
* [ ] Use one consistent frequency: daily, weekly, or monthly.
* [ ] Do not skip expected dates within the selected frequency.
* [ ] For weekly data, use a consistent week start day.
* [ ] For monthly data, use the first day of each month.
* [ ] Include enough history to capture trend, seasonality, and changes in media activity. Two years of daily or weekly data is a useful starting point. Monthly models generally require a longer history.

### Data Value and Integrity Rules

* [ ] Use numeric values for spend, impressions, clicks, and KPI fields.
* [ ] Do not include currency symbols or thousands separators in numeric cells.
* [ ] Do not leave numeric values blank. Use `0` when the measured activity did not occur.
* [ ] Use `1` and `0` for binary event variables such as a promotion flag.
* [ ] Keep the data type consistent within each column.
* [ ] Confirm that each paid row has a channel and a spend column.

## Data-to-Feature Ratio

A model needs enough observations relative to the number of parameters it estimates. Each media channel with adstock and saturation applied contributes several fitted parameters rather than one, and any trend or seasonality components estimated from the same data add further parameters. A model with 10 media channels and 15 other variables is therefore estimating well over 50 quantities, not 25.

As a practical minimum, maintain at least four observations for every fitted parameter counted this way. The requirement is better expressed in calendar time than in row count: two years of weekly data is the working target, and one year is the minimum, since separating yearly seasonality from trend requires two full cycles. One hundred daily observations covers roughly three months and cannot support this regardless of how the ratio appears.

Sample size alone does not identify coefficients; independent variation in spend does. Two channels that move together for 200 weeks are no more separable than they would be at 20. Before relying on a fit, review the coefficient of variation for each channel, the pairwise correlation between channel spends, and the number of distinct spend regimes each channel exhibits. A channel whose spend never varies remains unidentified at any sample size.

## Uploading the CSV in Lifesight&#x20;

1. Select **Models** from the sidebar and click `Create Model`.
2. In the Variables step, choose **Upload a CSV**.
3. Select the date column and map the Outcome KPI.
4. Add paid, organic, contextual, and halo variables.
5. Review any unused fields before proceeding.

**\[VIDEO PLACEHOLDER: Uploading and mapping an MMM CSV in Lifesight 4.0]**

## Troubleshooting and Support

If the file cannot be read, confirm that it is a CSV with a valid header row and is below the upload limit. For missing data, unusual time series, or questions about variable selection, contact your Lifesight Marketing Science team before replacing values or removing fields.