---
title: Google Sheets MMM data integration
excerpt: Connect Google Sheets data to a Lifesight 4.0 MMM workflow.
deprecated: false
hidden: true
metadata:
  title: Google Sheets MMM data integration
  robots: noindex
---
# Google Sheets MMM Data Integration

The Google Sheets integration lets you bring the marketing and business data you already maintain in spreadsheets straight into Lifesight, so your MMM (Marketing Mix Modeling) results stay current without manual uploads. <br /><br />After connecting the source, organize the data in a Data Model (a structured view that maps your data to the fields Lifesight needs) and use that Data Model to create or update an MMM workflow.

\[IMAGE PLACEHOLDER: Google Sheets integration in the Integrations workspace]

## Set your sheet up for success

A well-structured sheet connects cleanly and keeps your models running smoothly with every update. Before connecting your data, confirm that:

- **The first row contains clear column names.** For example, "Date," "Meta Spend," and "Revenue" rather than blank or generic headers.
- **Date values use a consistent format.** Mixing formats such as 09/01/2026 and 1 Sep 2026 in the same column can cause errors.
- **Media spend, KPI, and contextual columns are numeric where applicable.** KPI columns hold the outcome you want to measure, such as revenue or orders. Contextual columns hold external factors, such as pricing or weather. Remove currency symbols or text from numeric cells.
- **The selected range contains no merged cells or decorative rows.** Titles, notes, or subtotal rows inside the range can interfere with how data is read.
- **Column names stay stable between updates.** Renaming a column can break the connection between your sheet and your model.

See **CSV Data Formatting Guidelines** for the expected MMM data structure. The same modeling principles apply to data sourced from Google Sheets.

## Connect your sheet

1. Go to **Integrations**.
2. Select **Google Sheets**.
3. Authenticate the Google account that can access the sheet.
4. Select the spreadsheet, worksheet, and data range.
5. Review the detected schema (the columns and data types Lifesight has identified in your sheet) and complete the connection.

Reviewing the detected schema before you finish helps you catch any columns read as the wrong type, such as a spend column detected as text.

## Map your data for modeling

Create or select a Data Model that includes the connected Google Sheets data. Then map the variables required for Marketing Mix Modeling:

- **Date:** the time period for each row of data.
- **KPI:** the outcome you want to measure, such as revenue or conversions.
- **Paid media:** spend and activity for your paid channels.
- **Organic:** unpaid activity, such as email or organic social.
- **Contextual:** external factors that influence your results, such as pricing, promotions, or seasonality.

Mapping each variable correctly ensures it plays the right role in your model and is credited accurately in your results.

\[IMAGE PLACEHOLDER: Data Model with Google Sheets fields mapped for MMM]

## Put your data to work

**Create a new model**

When creating a model, select the prepared Data Model as the source. Then continue through **Variables**, **Configuration**, **Calibration**, **Relationships**, and **Review & Submit**.

**Update an existing model**

When new observations are available, start the first refresh from the model's action menu in **Model List**. Provide the updated data, then review **Diagnostics** and **Contribution** before using the refreshed result. This confirms the new data has been absorbed as expected and that model quality has held up.

## Keep the integration running smoothly

Keep field names and data types consistent as the sheet changes. If a source column is renamed, removed, or changes type, review the integration and Data Model before creating or refreshing a model. For example, if "FB Spend" is renamed to "Meta Spend," update the mapping in your Data Model so the model continues to read it correctly.

\[IMAGE PLACEHOLDER: Integration status and latest synchronization details]

***

## Frequently Asked Questions

**What kind of data can I bring in through Google Sheets?**
Any regularly maintained marketing and business data used for MMM, including media spend, KPIs, organic activity, and contextual factors.

**How should I format my sheet?**
Use clear column names in the first row, a consistent date format, numeric values for spend, KPI, and contextual columns, and no merged cells or decorative rows in the selected range. See **CSV Data Formatting Guidelines** for the full expected structure.

**Which Google account should I connect?**
Authenticate the Google account that has access to the sheet you want to use.

**Can I connect only part of a sheet?**
Yes. You select the spreadsheet, worksheet, and data range during setup.

**What is a Data Model, and why do I need one?**
A Data Model organizes your connected data and maps it to the variables MMM needs, such as date, KPI, paid media, organic, and contextual variables. You select it as the source when creating or updating a model.

**How do I use new data in an existing model?**
Start a refresh from the model's action menu in **Model List**, provide the updated data, and review **Diagnostics** and **Contribution** before using the refreshed result.

**What happens if I rename or remove a column in my sheet?**
The change can affect how Lifesight reads your data. Review the integration and Data Model before creating or refreshing a model, and update any mappings that have changed.

**Why is a column being read as the wrong type?**
This usually happens when a numeric column contains text, symbols, or blank rows. Clean the column so it contains only numeric values, then review the detected schema again.

**Can I change the data range after connecting?**
Review the integration settings to update the connection. After any change, check the Data Model to confirm all variables are still mapped correctly.