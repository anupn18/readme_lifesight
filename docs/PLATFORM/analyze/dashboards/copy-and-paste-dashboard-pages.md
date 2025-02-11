---
title: Copy and paste Dashboard pages
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
You can copy a page from one Dashboard to another, and from one page to another.

## Requirements

- When copy and pasting between Dashboards, both Dashboards must belong to the same organization.
- When copy and pasting between Dashboards, both Dashboards must use the same layout style. You cannot copy a page from an old layout to the new grid layout. 
- For one or multiple Dashboards, your account type must be Pro or Admin, or be a custom account type with the Edit Dashboard or Explore Dashboard permission enabled.
- You must be the Dashboard owner or be granted Can edit or Can explore Dashboard permission on one or multiple Dashboards.

## Tips for copy and pasting Dashboard pages

- Lifesight copies the whole page, plus dependent sources for elements on the page, even if the sources are not on the page. For sources that are not on the page, Lifesight creates a second page with the naming convention “Page Name - Dependencies”.
  - If the user performing the copy operation does not have access permissions to the source data of an element on the page, Lifesight will copy and paste it, but the user will not see the data and pasted elements may show a permissions error message.
- Linked input tables are not supported when copy and pasting Dashboard pages. Lifesight can copy empty input tables and all data, UI, and control elements.
- If you only need to copy elements on the page, consider doing that.

## Copy and paste a page

1. From the page menu, select Copy page. Lifesight copies the page.
2. (Optional) Click out of the copy confirmation message, or wait a few seconds for it to disappear.
3. Paste the copied page.
   1. If copying to the same Dashboard, press cmd/ctrl-v or right-click and select Paste.  
      Lifesight pastes the new page into the Dashboard and appends "Copy" to the page name.
   2. If copying to another Dashboard, go to the Dashboard and enter Edit mode. Press cmd/ctrl-v or right-click and select Paste.  
      Lifesight pastes the new page into the Dashboard and appends "Copy" to the page name.  
      If there are dependencies, Lifesight pastes them into another page and appends "Dependencies" to the page name.
4. Edit the new, copied page as you like.