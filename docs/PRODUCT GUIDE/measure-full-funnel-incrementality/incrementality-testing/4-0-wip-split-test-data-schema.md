---
title: '[4.0][WIP] Split test data schema'
excerpt: Lifesight 4.0 WIP guide for Split test data schema.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
# Split Test Data Schema

Lifesight 4.0 does not currently expose the legacy audience Split Test workflow, so there is no active Split Test upload schema in the platform.

[IMAGE PLACEHOLDER: Geo Testing data upload in Lifesight 4.0]

For the available **Geo Testing** workflow, upload a CSV with:

- A date column
- A geo column
- A numeric primary KPI column
- Parent geo columns when required by the selected granularity
- Optional spend and secondary KPI columns

The file must use one consistent date format and daily or weekly granularity. Keep market labels and KPI definitions stable throughout the pre-treatment period.

See **Geo Test Data Schema** for the complete 4.0 requirements.

> Do not upload user assignment or treatment-group data into the Geo Testing flow. Geo Testing expects aggregated observations by market and date.
