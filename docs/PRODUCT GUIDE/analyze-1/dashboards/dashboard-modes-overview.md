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

<HTMLBlock>{`
<table style="width: 100%; border-collapse: collapse;">
<thead>
<tr>
  <th style="border: 1px solid #ddd; padding: 8px;"></th>
  <th style="border: 1px solid #ddd; padding: 8px;">View mode<br>(Can view)</th>
  <th style="border: 1px solid #ddd; padding: 8px;">View mode<br>(Can explore / Can edit)</th>
  <th style="border: 1px solid #ddd; padding: 8px;">Explore mode<br>(Can explore / Can edit)</th>
  <th style="border: 1px solid #ddd; padding: 8px;">Edit mode<br>(Can edit)</th>
</tr>
</thead>
<tbody>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Update control values</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Modify existing filters</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Sort column data</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View column details</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Expand/collapse grouped rows</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View aggregated underlying data</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Refresh data</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Create bookmarks</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View and add comments <em>1</em></p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Create new filters</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View and drill into unaggregated underlying data</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Use drill paths (&quot;Drill anywhere&quot;)</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Format, reorder, rename, hide, freeze, and delete columns</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Enter input table values <em>2</em></p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Download individual elements to PNG</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Download individual elements to CSV, Excel, JSON, Google Sheets, or PDF <em>3</em></p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Send or schedule exports <em>4</em></p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Copy data point values</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Create, edit, and delete pages</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Create, edit, and delete elements<br>(editing encompasses properties, format, actions, columns, etc.)</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Duplicate and move existing elements</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Copy/paste elements</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View and change element data<br>sources</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Add and modify columns</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View custom SQL logic</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Edit layouts and dashboard settings</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View lineage</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>View hidden pages</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
<tr>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>Publish dashboard edits</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>❌</p>
</td>
  <td style="border: 1px solid #ddd; padding: 8px;"><p>✅</p>
</td>
</tr>
</tbody>
</table>
`}</HTMLBlock>


<br />

- _1 Requires an account type with the Can comment on Dashboards permission enabled._
- _2 Requires the input table element's data entry permission to be set to the Dashboard's published version._
- _3 The ability to download to CSV, Excel, JSON, and PDF requires an account type with the Download permission enabled. The ability to download to Google Sheets also requires the Export to Google Sheet permission._
- _4 The ability to send ad hoc exports requires an account type with the Export to Email or relevant destination permission enabled. The ability to schedule exports requires the Schedule export permission._