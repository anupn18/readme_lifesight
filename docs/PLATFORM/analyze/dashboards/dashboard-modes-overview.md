---
title: Dashboard Modes Overview
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
Lifesight features three Dashboard modes (View, Explore, and Edit) that provide different levels of interactions, customizations, and analysis within a Dashboard. Each mode is designed to help you perform specific tasks depending on your objectives and permissions.

## Dashboard mode objectives

|                                      | View Mode                                                                                                       | Explore Mode                                                                                                                                                                  |  Edit Mode                                                                                                                                   |
| :----------------------------------- | :-------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| **Purpose**                          | Allows you to view a published version of a Dashboard (the version labeled “Published” and all tagged versions) | Provides an isolated environment in which you can customize published Dashboard content and perform ad hoc analysis without affecting saved or shared versions of a Dashboard | Provides a draft environment with full-scope analytic functionality that allows you to edit and save an individual or collaborative analysis |
| **Use Case**                         | Recommended when you need to view prepared data and insights without performing additional analysis.            | Recommended when you need quick answers to specific business questions, but you don’t need to save the analysis for future use or sharing                                     | Recommended when you need to build reports and publish them for future use or sharing                                                        |
| **Required account type permission** | View Dashboards or Basic explore                                                                                | Full Explore                                                                                                                                                                  | Create, edit, and publish Dashboards                                                                                                         |
| **Required dashboard permission**    | Can view, Can explore, Can edit, or Owner                                                                       | Can explore, Can edit, or Owner                                                                                                                                               | Can edit or Owner                                                                                                                            |

<br />

## Dashboard accessibility comparison

The following table compares what you can do in each mode based on dashboard permission.

[block:parameters]
{
  "data": {
    "h-0": "",
    "h-1": "View mode  \n(Can view)",
    "h-2": "View mode  \n(Can explore / Can edit)",
    "h-3": "Explore mode  \n(Can explore / Can edit)",
    "h-4": "Edit mode  \n(Can edit)",
    "0-0": "Update control values",
    "0-1": "✅",
    "0-2": "✅",
    "0-3": "✅",
    "0-4": "✅",
    "1-0": "Modify existing filters",
    "1-1": "✅",
    "1-2": "✅",
    "1-3": "✅",
    "1-4": "✅",
    "2-0": "Sort column data",
    "2-1": "✅",
    "2-2": "✅",
    "2-3": "✅",
    "2-4": "✅",
    "3-0": "View column details",
    "3-1": "✅",
    "3-2": "✅",
    "3-3": "✅",
    "3-4": "✅",
    "4-0": "Expand/collapse grouped rows",
    "4-1": "✅",
    "4-2": "✅",
    "4-3": "✅",
    "4-4": "✅",
    "5-0": "View aggregated underlying data",
    "5-1": "✅",
    "5-2": "✅",
    "5-3": "✅",
    "5-4": "✅",
    "6-0": "Refresh data",
    "6-1": "✅",
    "6-2": "✅",
    "6-3": "✅",
    "6-4": "✅",
    "7-0": "Create bookmarks",
    "7-1": "✅",
    "7-2": "✅",
    "7-3": "✅",
    "7-4": "✅",
    "8-0": "View and add comments _1_",
    "8-1": "✅",
    "8-2": "✅",
    "8-3": "✅",
    "8-4": "✅",
    "9-0": "Create new filters",
    "9-1": "❌",
    "9-2": "✅",
    "9-3": "✅",
    "9-4": "✅",
    "10-0": "View and drill into unaggregated underlying data",
    "10-1": "❌",
    "10-2": "✅",
    "10-3": "✅",
    "10-4": "✅",
    "11-0": "Use drill paths (\"Drill anywhere\")",
    "11-1": "❌",
    "11-2": "✅",
    "11-3": "✅",
    "11-4": "✅",
    "12-0": "Format, reorder, rename, hide, freeze, and delete columns",
    "12-1": "❌",
    "12-2": "✅",
    "12-3": "✅",
    "12-4": "✅",
    "13-0": "Enter input table values _2_",
    "13-1": "❌",
    "13-2": "✅",
    "13-3": "✅",
    "13-4": "✅",
    "14-0": "Download individual elements to PNG",
    "14-1": "❌",
    "14-2": "✅",
    "14-3": "✅",
    "14-4": "✅",
    "15-0": "Download individual elements to CSV, Excel, JSON, Google Sheets, or PDF _3_",
    "15-1": "❌",
    "15-2": "✅",
    "15-3": "✅",
    "15-4": "✅",
    "16-0": "Send or schedule exports _4_",
    "16-1": "❌",
    "16-2": "✅",
    "16-3": "✅",
    "16-4": "✅",
    "17-0": "Copy data point values",
    "17-1": "❌",
    "17-2": "✅",
    "17-3": "✅",
    "17-4": "✅",
    "18-0": "Create, edit, and delete pages",
    "18-1": "❌",
    "18-2": "❌",
    "18-3": "✅",
    "18-4": "✅",
    "19-0": "Create, edit, and delete elements  \n(editing encompasses properties, format, actions, columns, etc.)",
    "19-1": "❌",
    "19-2": "❌",
    "19-3": "✅",
    "19-4": "✅",
    "20-0": "Duplicate and move existing elements",
    "20-1": "❌",
    "20-2": "❌",
    "20-3": "✅",
    "20-4": "✅",
    "21-0": "Copy/paste elements",
    "21-1": "❌",
    "21-2": "❌",
    "21-3": "✅",
    "21-4": "✅",
    "22-0": "View and change element data  \nsources",
    "22-1": "❌",
    "22-2": "❌",
    "22-3": "✅",
    "22-4": "✅",
    "23-0": "Add and modify columns",
    "23-1": "❌",
    "23-2": "❌",
    "23-3": "✅",
    "23-4": "✅",
    "24-0": "View custom SQL logic",
    "24-1": "❌",
    "24-2": "❌",
    "24-3": "✅",
    "24-4": "✅",
    "25-0": "Edit layouts and dashboard settings",
    "25-1": "❌",
    "25-2": "❌",
    "25-3": "✅",
    "25-4": "✅",
    "26-0": "View lineage",
    "26-1": "❌",
    "26-2": "❌",
    "26-3": "✅",
    "26-4": "✅",
    "27-0": "View hidden pages",
    "27-1": "❌",
    "27-2": "❌",
    "27-3": "❌",
    "27-4": "✅",
    "28-0": "Publish dashboard edits",
    "28-1": "❌",
    "28-2": "❌",
    "28-3": "❌",
    "28-4": "✅"
  },
  "cols": 5,
  "rows": 29,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


<br />

- _1 Requires an account type with the Can comment on Dashboards permission enabled._
- _2 Requires the input table element's data entry permission to be set to the Dashboard's published version._
- _3 The ability to download to CSV, Excel, JSON, and PDF requires an account type with the Download permission enabled. The ability to download to Google Sheets also requires the Export to Google Sheet permission._
- _4 The ability to send ad hoc exports requires an account type with the Export to Email or relevant destination permission enabled. The ability to schedule exports requires the Schedule export permission._