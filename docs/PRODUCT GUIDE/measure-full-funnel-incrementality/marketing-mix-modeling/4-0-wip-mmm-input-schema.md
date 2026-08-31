---
title: '[4.0][WIP] CSV Data Formatting Guidelines'
excerpt: Prepare CSV data for Marketing Mix Modeling in Lifesight 4.0.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
High-quality input data is the foundation of an accurate and actionable Marketing Mix Model. In Lifesight 4.0, you can create a model from an existing Data Model or upload a CSV file and map every field manually.

### CSV Template

Use the sample template as a starting point for your file.

[<button>View MMM CSV Sample Template</button>](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1915444742#gid=1915442)

**[IMAGE PLACEHOLDER: Example MMM CSV with date, KPI, spend, impressions, clicks, and control columns]**

## Data Requirements

Your CSV must contain the fields required to define the model's outcome, paid media, and time window.

### Mandatory Columns

* **Date Column:** A date field in `YYYY-MM-DD` format.
* **KPI Column:** At least one outcome you want to model, such as `Revenue`, `Orders`, `Installs`, or `New_Customers`.
* **Paid Media Spend:** At least one numeric spend field for a paid channel or tactic.

The 4.0 variable mapper requires a channel and spend field for every paid row. Tactic, impressions, and clicks are optional.

### Recommended Additional Columns

| Category | Recommended variables |
| :--- | :--- |
| **Paid Media** | Spend, impressions, and clicks at the channel or tactic level |
| **Organic** | Organic sessions, direct traffic, email activity, or other owned and earned signals |
| **Contextual** | Promotions, pricing changes, holidays, weather, competitor activity, or macro indicators |
| **Halo** | Cross-channel or cross-product variables used to represent spillover effects |
| **Dimensions** | Country, region, product, or another field used to fit dimensional child models |

For organic, contextual, and halo variables, you will select a Positive, Negative, or Neutral impact during model creation.

## Formatting and Validation Checklist

> 🚧 Review the file before uploading it. A clean header row and consistent time series make mapping and validation much easier.

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

A model needs enough observations relative to the number of independent variables. As a practical minimum, maintain at least four data points for every independent variable.

For example, a dataset with 25 independent variables should contain at least 100 observations. More history is often required when the data contains strong seasonality, low spend variation, or many related channels.

## Uploading the CSV in Lifesight 4.0

1. Select **Models** from the sidebar and click **`Create Model`**.
2. In the Variables step, choose **Upload a CSV**.
3. Select the date column and map the Outcome KPI.
4. Add paid, organic, contextual, and halo variables.
5. Review any unused fields before proceeding.

**[VIDEO PLACEHOLDER: Uploading and mapping an MMM CSV in Lifesight 4.0]**

## Troubleshooting and Support

If the file cannot be read, confirm that it is a CSV with a valid header row and is below the upload limit. For missing data, unusual time series, or questions about variable selection, contact your Lifesight Marketing Science team before replacing values or removing fields.