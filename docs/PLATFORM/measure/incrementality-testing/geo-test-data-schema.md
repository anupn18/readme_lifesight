---
title: Geo test data schema
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
When uploading Geo Test data via CSV or Integrated method, ensure your data follows the provided template. A consistent data schema is crucial for tracking performance across geographic regions. Below is a typical schema with key attributes for analysis.

### View [Geo schema template](https://docs.google.com/spreadsheets/d/1kNy-pcGCp6E4G1LbXIZBtB1YItGdD0LcWo3ScwE1wQw/edit?gid=1915444742#gid=1915444742)

## Schema

| Field Name | Data type | Description                                         | Example    |
| :--------- | :-------- | :-------------------------------------------------- | :--------- |
| Date       | Date      | The date when the metric was recorded.              | 01-01-2023 |
| Geography  | String    | Name of state/city/zip code                         | California |
| KPI        | Numeric   | Value of the captured metric (Revenue, Orders, etc) | 19,707     |

<br />

## Minimum data requirements to run a geo test:

* Historical KPI Data of at least 6 months
* Dates
* Geographies
