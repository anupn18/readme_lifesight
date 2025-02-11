---
title: Dashboard Overview
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
Lifesight Dashboards are data exploration tools for both Business Intelligence (BI) developers and spreadsheet-savvy analysts. Dashboards are similar to spreadsheets in that they have pages and display data in tables and pivot tables. Dashboards are similar to BI tools in that they provide Dashboard-like displays that can include charts, graphs, controls, tables, texts, and images. You analyze your data and create visualizations on Dashboard pages, and use a page as a Dashboard.

Dashboards enable both ad hoc data exploration and complex BI presentations and reporting. The collaborative interface and visual approach to data interaction in Lifesight makes data accessible to everyone in your organization, and teams can draw insights from large amounts of data.

This document introduces you to Dashboards and links to more resources.

## **Dashboard lifecycle states**

Dashboards have three states: explore, draft, and publish.  
When you create a Dashboard, it is in an explore state until you actively save the first version. You can keep a Dashboard in the explore state and never save it. For example, you might need to conduct ad hoc data exploration and analysis that is only needed in the current moment, and you don't want to clutter folders with one-off documents. Unsaved Dashboards are called explorations and are available in the Recents page for 30 days.  
Save a Dashboard to continue your analysis and set up reporting. Saving also publishes the Dashboard, but only you have access until you share the Dashboard.

## **Data used in Dashboards**

Dashboards can use data from multiple sources, including tables in a Cloud Data Warehouse (CDW) and your organization's Lifesight datasets. Your data is always live, accessible at scale, and cannot be deleted or corrupted. After Lifesight connects to your data source, you can create Dashboards directly from tables in your source, or you can model the data using a Lifesight dataset. Use a dataset as the source for your Dashboards to ensure consistency.

When users access a Dataset or Dashboard that has been shared with them, that document owner's permission to the source data is evaluated within Lifesight and the queries to the cloud data warehouse are run using the user account credentials specified in the connection settings. However, if the connection is configured to use OAuth without a service account, the queries run with the user's personal OAuth credentials configured for the data warehouse. If the connection is configured to use OAuth with a service account, an admin can configure individual Dashboards to use the service account credentials.

Lifesight provides a variety of settings that affect the editing environment, formatting and theme, and page breaks for PDF exports.

## **What's in a Dashboard**

This section introduces you to the basic components of Dashboards. The screenshots show a Dashboard in Edit mode.  
Pages and page tabs  
A Dashboard contains one or more pages. Page tabs, located at the bottom of the screen, show different pages in the Dashboard.

## **Page menu**

Each page has a menu. When a Dashboard is in view mode, such as when it is provided to Viewers, users can export (download) a page as a PDF-formatted file. 

In edit mode, users have more options for pages, including delete, rename, hide, duplicate, and add a new page. For more information about hiding pages, see Manage Dashboard page visibility.

## **Page canvas**

Each Dashboard page has a canvas on which you can place elements such as tables, pivot tables, text, controls, images, and visualizations.

## **Editor panel**

The Dashboard editor panel, on the left side of the screen, allows you to interact with and update elements in your Dashboard.  
When you select a new or existing element, the editor panel automatically displays that specific element’s configuration.  
The editor panel content changes depending on how you are currently interacting with the Dashboard. For example, it displays one view when adding a new element and alternative views when configuring different element types.  
Access to the editor panel depends on your Dashboard view mode.

## **Elements**

You arrange elements on the page canvas. Element types include:  
Data elements (tables, visualizations, and pivot tables)  
UI elements (text, images, buttons, embeds, and spacers)  
Control elements (filters and parameters)  
In Dashboards, tables and pivot tables are not considered types of visualizations. Visualizations, tables, and pivot tables are separate elements in the data elements category.  
For more information about elements see Intro to element types.

## **Toolbar and formula bar**

The toolbar, located directly under the Dashboard header, gives you quick access to select actions, formatting options, and the formula bar. The toolbar content changes depending on the element you have selected, and undo, redo, and page theming functions are always displayed.  
{The formula bar lets you calculate values based on Lifesight functions, much like a spreadsheet. See Orientation for spreadsheet users and Popular functions.  
When you select a column in a data element, you can view and edit the column's formula in the toolbar only if you have Can Edit or Can Explore access to the Dashboard. For more information see Folder and Document Permission.