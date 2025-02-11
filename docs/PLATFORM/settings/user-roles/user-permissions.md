---
title: User permissions
excerpt: View permissions for each user role.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Measure module

| Feature | Access                    | Manager | Admin | Billing admin | Support | Viewer |
| :------ | :------------------------ | :------ | :---- | :------------ | :------ | :----- |
| MMM     | Create MMM Model          | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Delete MMM Model.         | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Reconfigure MMM Model     | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Download Budget Worksheet | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Refresh MMM Model         | ✅       | ✅     | ✅             | ✅       | ❌      |

| Feature     | Access                                                     | Manager | Admin | Billing admin | Support | Viewer |
| :---------- | :--------------------------------------------------------- | :------ | :---- | :------------ | :------ | :----- |
| Experiments | Create Experiment                                          | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Delete Experiment                                          | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Refresh Experiment                                         | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Stop Experiment                                            | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Markets Complete Experiment Status                         | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Markets Ready Next Button                                  | ✅       | ✅     | ✅             | ✅       | ❌      |
|             | Upload data for Failed Status and Awaiting Data for upload | ✅       | ✅     | ✅             | ✅       | ❌      |

| Feature | Access                    | Manager | Admin | Billing admin | Support | Viewer |
| :------ | :------------------------ | :------ | :---- | :------------ | :------ | :----- |
| Causal  | Create Causal Model       | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Delete Causal Model       | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | Re-Discover Causal Model  | ✅       | ✅     | ✅             | ✅       | ❌      |
|         | What-If Analysis Creation | ✅       | ✅     | ✅             | ✅       | ❌      |

[block:parameters]
{
  "data": {
    "h-0": "Feature",
    "h-1": "Access",
    "h-2": "Manager",
    "h-3": "Admin",
    "h-4": "Billing admin",
    "h-5": "Support",
    "h-6": "Viewer",
    "0-0": "Attribution  ",
    "0-1": "Toggle for Campaigns,  \nAdGroups and Ads",
    "0-2": "✅",
    "0-3": "✅",
    "0-4": "✅",
    "0-5": "❌",
    "0-6": "❌"
  },
  "cols": 7,
  "rows": 1,
  "align": [
    "left",
    "left",
    "left",
    "left",
    "left",
    "left",
    "left"
  ]
}
[/block]


***

## Action module

| Feature         | Access                                                             | Manager | Admin | Billing admin | Support | Viewer |
| :-------------- | :----------------------------------------------------------------- | :------ | :---- | :------------ | :------ | :----- |
| Planner         | Create Planner                                                     | ✅       | ✅     | ✅             | ✅       | ❌      |
|                 | Delete Planner                                                     | ✅       | ✅     | ✅             | ✅       | ❌      |
| Recommendations | The CTA buttons for Recommendations: View, Connect, Reconnect, Run | ✅       | ✅     | ✅             | ✅       | ❌      |

***

## Analyze module

| Feature   | Access                  | Manager | Admin | Billing admin | Support | Viewer |
| :-------- | :---------------------- | :------ | :---- | :------------ | :------ | :----- |
| Customers | Adding new RFM Segments | ✅       | ✅     | ✅             | ✅       | ❌      |

***

## Connect module

| Feature  | Access                       | Manager | Admin | Billing admin | Support | Viewer |
| :------- | :--------------------------- | :------ | :---- | :------------ | :------ | :----- |
| Segment  | Create Segment               | ✅       | ✅     | ✅             | ✅       | ❌      |
|          | Refresh Segment              | ✅       | ✅     | ✅             | ✅       | ❌      |
|          | Sync Settings                | ✅       | ✅     | ✅             | ❌       | ❌      |
|          | Editing Segments and Refresh | ✅       | ✅     | ✅             | ✅       | ❌      |
| Profiles | GDPR Export and Delete       | ✅       | ✅     | ✅             | ❌       | ❌      |
| List     | Create List                  | ✅       | ✅     | ✅             | ✅       | ❌      |
|          | Quick Add                    | ✅       | ✅     | ✅             | ❌       | ❌      |
|          | Import Contacts              | ✅       | ✅     | ✅             | ❌       | ❌      |

***

## Settings

| Feature                | Access                    | Manager | Admin | Billing admin | Support                           | Viewer |
| :--------------------- | :------------------------ | :------ | :---- | :------------ | :-------------------------------- | :----- |
| Rules & Labelling      | Create Rule               | ✅       | ✅     | ✅             |                                   | ❌      |
|                        | Delete Rule               | ✅       | ✅     | ✅             |                                   | ❌      |
|                        | Active Toggle             | ✅       | ✅     | ✅             |                                   | ❌      |
| User & Team management | Invite user               | ✅       | ✅     | ✅             | YES (All Roles including MANAGER) | ❌      |
|                        | Delete user               | ✅       | ✅     | ✅             | ❌                                 | ❌      |
| Compliance             | Download CTA for Exported | ✅       | ✅     |               | ❌                                 | ❌      |
| Workspace              | Create New Workspace      | ✅       | ❌     |               | ❌                                 | ❌      |