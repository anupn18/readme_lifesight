---
title: Manage Dashboard refresh options
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
Lifesight refreshes Dashboard data every time an individual opens or refreshes the Dashboard. If you want to refresh Dashboard data on a set schedule, such as for a Dashboard displayed on a screen without user interaction, you can set a custom refresh schedule.

Data elements can also be refreshed individually, but not on an automated schedule.

## Requirements

- To set up a refresh schedule, you must have Can Edit access to the individual Dashboard and you must be assigned an account type with the Set Dashboard data refresh permission enabled.
- If your Dashboard is embedded in a host application, the secure embed must be authenticated with JSON Web Tokens (JWTs) for a custom refresh schedule to apply to the embedded content.

## Setup up a refresh schedule

To set up a refresh schedule for a Dashboard, do the following:

1. Click the More options to the right of the refresh button in the Dashboard header.
2. Select Data refresh.  
   The Data refresh settings modal opens.
3. For the Refresh schedule, turn on the Enable toggle. 
4. Adjust the Query data every field to specify how often to refresh the Dashboard. For example, every 10 minutes.
5. [optional] To limit the refresh schedule to a specific time window, enter times in the Between fields. Lifesight uses the browser timezone to evaluate whether the refresh schedule should be in effect.
6. Click Save.

## Refresh individual data elements

You can manually refresh the data in an individual data element.

1. Select the data element.
2. In the element toolbar, click More.
3. Click Refresh data.

The data in the element refreshes.