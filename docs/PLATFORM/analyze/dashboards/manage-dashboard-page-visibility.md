---
title: Manage Dashboard page visibility
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
By default, Dashboard pages are visible to all users with permission to view, explore, or edit the Dashboard. You can change the visibility of individual pages to restrict viewing specific Dashboard content.

This document describes Lifesight’s page visibility options and explains how to customize the visibility of a particular page.

## User requirements

The ability to manage Dashboard page visibility requires the following:

- You must be assigned an account type with the Create, edit, and publish Dashboards permission enabled.
- You must be the Dashboard owner or be granted Can edit Dashboard permission.

## Understanding page visibility

Page visibility is not a security feature

### Page visibility in Dashboard versions and secure embeds

#### Tagged versions

Tagged Dashboard versions inherit the page visibility settings saved to the Dashboard when the tag is applied. Therefore, a page can be accessible to a user in one version and hidden from the same user in another.

#### Secure embeds

Page visibility in secure embeds is determined by team settings. A page is only visible to an embed user when shown to the user’s assigned team (via Show page to all users or Only show to select users or teams).

## Hide or unhide a page

Use the Hide page and Unhide page options to quickly update the page visibility for all users.

1. Open a Dashboard in Edit mode.
2. Locate the tab for the page you want to customize.
3. Click the drop-down in the tab to open the page menu, then select the available option:

<br />

[block:parameters]
{
  "data": {
    "h-0": "",
    "h-1": "",
    "0-0": "Hide Page",
    "0-1": "Hides page from all users accessing the workbook in View or Explore mode.  \n_Available when the page is currently visible to all users._",
    "1-0": "Unhide Page",
    "1-1": "Shows page to all users accessing the Dashboard in any mode.  \n_Available when the page is currently hidden from all or select users and teams._"
  },
  "cols": 2,
  "rows": 2,
  "align": [
    "left",
    "left"
  ]
}
[/block]


## Customize page visibility

Use the Customize page visibility option to update the page visibility for all users or specific users and teams.

1. Open a Dashboard in Edit mode.
2. Locate the tab for the page you want to customize.
3. Click the drop down in the tab to open the page menu, then select Customize page visibility.
4. In the Customize Page Visibility modal, configure the page visibility:

   1. Click the Page visibility setting field and select an option from the dropdown:

   <br />

   |                                    |                                                                                                                               |
   | :--------------------------------- | :---------------------------------------------------------------------------------------------------------------------------- |
   | Hide page from all users           | Hides page from all users accessing the Dashboard in View or Explore mode.                                                    |
   | Show page to all users  (default)  | Shows page to all users accessing the Dashboard in any mode.                                                                  |
   | Only show to select users or teams | Only shows page to selected users and teams. Hides page from remaining users accessing the Dashboard in View or Explore mode. |

   1. If you selected Only show to select users or teams in step 4i, use the Select users field to search for and select applicable users and teams.
   2. Click Save to apply the page visibility change.