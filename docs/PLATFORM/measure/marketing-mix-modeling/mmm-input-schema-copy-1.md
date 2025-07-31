---
title: CSV Data Formatting Guidelines
excerpt: 'Data Validation & Formatting rules for CSV upload '
deprecated: false
hidden: true
metadata:
  robots: index
next:
  pages:
    - slug: model-creation-copy
      title: Model creation
      type: basic
---
High-quality input data is the foundation of an accurate and actionable Marketing Mix Model (MMM). To ensure the Lifesight UMM Platform can process your data effectively, please adhere to the following formatting and validation guidelines.

### CSV Template

To get started quickly, we recommend using our sample template. It provides a ready-to-use structure for your data.

[<button>View MMM CSV Sample Template</button>](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1915444742#gid=1915442)

***

## Data Requirements

Your input file is built on a combination of mandatory and recommended data columns.

### Mandatory Columns

Your CSV file **must** include the following three attributes for the model to run. While you can customize the header names, the data they represent is essential.

* **Date Column:** A date field in `yyyy-mm-dd` format. Example: `{{your_date_column}}`.
* **KPI Column:** At least one outcome Key Performance Indicator (KPI) you want to measure. Example: `{{your_kpi_column}}` like `Revenue` or `Installs` or `Orders`.
* **Paid Media Column:** At least one variable representing spend or impressions from a paid media channel. Example: `Google_Spend`, `CTV_Impressions`

<br />

### Recommended Additional Columns

> 👍 Enrich Your Model for Deeper Insights
>
> Including additional variables from the categories below will significantly improve the model's accuracy and provide a more holistic view of your marketing performance.

| Category                   | Recommended Input Variables                                                                                                                                                                                                 |
| :------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Organic & Owned**        | `Newsletter_CTR`, `Push_Notification_CTR`, `Social_Media_Impressions`, `Blog_Impressions`, `Social_Engagement_Rate`                                                                                                         |
| **Contextual & External**  | `Promotions_Active` (as 1/0), `Loyalty_Program_Signups`, `Competitor_Promotions`, `Seasonal_Events` (e.g., Black Friday), `Product_Releases`, `Price_Changes`                                                               |
| **Paid Media Granularity** | `Google_Search_Clicks`, `Google_Search_Impressions` `Meta_Retargeting_Clicks`, `Meta_Retargeting_Impressions` `Linear_TV_Spend`, `CTV_Spend`, `Affiliate_Spend`, `Influencer_Spend`, `KOL_Spend`, `Event_Sponsorship_Spend` |

***

## Formatting & Validation Checklist

> 🚧 Your file must pass all the following validation rules to be successfully uploaded and processed. Please review this checklist carefully.

### File & Header Rules

* [ ] **Column Headers:** Header names must contain only alphanumeric characters and underscores (`_`). They must start with a letter (e.g., `Meta_Spend`, not `_Meta_Spend`).
* [ ] **No Blank Rows/Columns:** Delete all empty rows and columns from your file.
* [ ] **No All-Zero Columns:** Ensure no single column contains `0` for all its values.

### Date & Time Rules

* [ ] **Date Format:** All dates must be in the **`YYYY-MM-DD`** format.
* [ ] **Consistent Frequency:** The time interval between dates must be consistent (daily, weekly, or monthly) throughout the file. Do not mix frequencies.
* [ ] **Weekly Data Alignment:** Dates for weekly data must represent the first day of the week (either Sunday or Monday). All metrics for a given week (e.g., Jan 1st to Jan 7th) should be aggregated under the date for the first day of that week (e.g., `2024-01-01`).
* [ ] **Monthly Data Alignment:** Dates for monthly data must be the first day of the month (e.g., `2024-01-01`, `2024-02-01`).
* [ ] **Complete Date Range:** Ensure there are no missing dates within your chosen frequency. For example, a weekly dataset should not skip any weeks.
* [ ] **Sufficient Historical Data:** We recommend providing at least **2 years** of historical data for daily or weekly granularity, and **3 years** for monthly granularity.

### Data Value & Integrity Rules

* [ ] **Numeric Values Only:** All metric columns (spend, impressions, clicks, etc.) must contain only numeric values. Do not include currency symbols (e.g., `$`) or commas.
* [ ] **Positive Values:** All values must be positive integers or zero.
* [ ] **No Missing Values:** There should be no `NULL` or empty cells. If a channel was not active during a period, its value must be populated with `0`.
* [ ] **Boolean Values:** For contextual variables that are either on or off (e.g., a promotion), use `1` for true/active and `0` for false/inactive.
* [ ] **Consistent Data Types:** Ensure all values within a single column are of the same data type.

<br />

## Data-to-Feature Ratio Explained

To ensure statistical validity, your dataset must maintain a minimum of 4:1 ratio of data points (rows): independent variables (columns).

**Example:**\
If you have **25** columns of independent variables in your CSV, you need at least **100** rows of data.

## Troubleshooting & Support

If you have missing data or need assistance with preparing your file, please reach out to your dedicated Marketing Science team at Lifesight for support. They can provide guidance on the best techniques for handling missing values, such as interpolation or rolling averages, to ensure your model's integrity.