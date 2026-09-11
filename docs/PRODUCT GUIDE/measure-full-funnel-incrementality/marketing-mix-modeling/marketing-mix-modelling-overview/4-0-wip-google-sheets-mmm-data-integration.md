---
title: '[4.0][WIP] Google sheets MMM data integration'
excerpt: Connect Google Sheets data to a Lifesight 4.0 MMM workflow.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Google Sheets MMM Data Integration

Use the Google Sheets integration to bring regularly maintained marketing and business data into Lifesight. After connecting the source, organize the data in a Data Model and use that Data Model to create or update an MMM workflow.

[IMAGE PLACEHOLDER: Google Sheets integration in the Integrations workspace]

## Prepare the sheet

Before connecting the data, confirm that:

- The first row contains clear column names
- Date values use a consistent format
- Media spend, KPI, and contextual columns are numeric where applicable
- The selected range does not contain merged cells or decorative rows
- Column names remain stable between updates

See **CSV Data Formatting Guidelines** for the expected MMM data structure. The same modeling principles apply to data sourced from Google Sheets.

## Connect Google Sheets

1. Go to **Integrations**.
2. Select **Google Sheets**.
3. Authenticate the Google account that can access the sheet.
4. Select the spreadsheet, worksheet, and data range.
5. Review the detected schema and complete the connection.

[VIDEO PLACEHOLDER: Connecting a Google Sheet and reviewing its schema]

## Create a Data Model

Create or select a Data Model that includes the connected Google Sheets data. Map the date, KPI, paid media, organic, and contextual variables required for Marketing Mix Modeling.

[IMAGE PLACEHOLDER: Data Model with Google Sheets fields mapped for MMM]

## Use the data in Marketing Mix Modeling

When creating a model, select the prepared Data Model as the source. Continue through Variables, Configuration, Calibration, Relationships, and Review & Submit.

For an existing model, start the first refresh from its action menu in Model List when new observations are available. Provide the updated data, then review Diagnostics and Contribution before using the refreshed result.

## Maintain the integration

Keep field names and data types consistent as the sheet changes. If a source column is renamed, removed, or changes type, review the integration and Data Model before creating or refreshing a model.

[IMAGE PLACEHOLDER: Integration status and latest synchronization details]