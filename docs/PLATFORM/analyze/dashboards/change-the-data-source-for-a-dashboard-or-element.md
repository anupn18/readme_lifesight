---
title: Change the data source for a Dashboard or element
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
You can change the data source used by an entire Dashboard or a specific data element.

For example, you might build a Dashboard with data sources from a test data connection to reduce load on a production database while you experiment and create calculations. When you're ready to publish and share the Dashboard with your team or organization, you can replace the test data sources used by the Dashboard with production data sources.

You can also change or swap the data source of a Dashboard automatically, based on the version tag of the Dashboard.

## Requirements

- You must be granted Can use data permission for the connection that you want to change to.
- You must have Can edit or Can explore permissions on the Dashboard.

## Swap the data source for a Dashboard

You can swap the data source for all elements in a Dashboard, for example to change from a test data warehouse connection to a production data warehouse connection, do the following:

1. Open the Dashboard in Edit or Explore mode.
2. From the Dashboard menu , select Swap data sources….
3. In the Swap Data Sources Overview modal, review the auto-selected Matching Connection. If needed, update the selected connection.
4. Review the Matching Data Sources for each element in the Dashboard. If any data sources have No Match, select Match Manually to choose a different data source for each element without a matching data source.
   1. On the manual match page, select a data source used by an element, then click Select Source.
   2. Search for or browse to a new data source, then click Select.
   3. Select the next data source that needs to be matched and repeat these steps.
   4. After all data sources without matches have been matched to a new data source, select Swap.
5. If none of your data sources need to be manually matched, select Swap Now.  
   The Dashboard updates to use the new data source. Any elements without matching data sources display an error.

> 📘 If your Dashboard contains input tables or custom SQL elements, the data source and connection for those elements is not swapped. Instead, you must recreate the elements with the new connection as the data source.
> 
> - For an input table, create an input table with the new connection then copy and paste the data from the old input table to the new one.
> - For a custom SQL element, create a new SQL element and write equivalent SQL against the new data connection.

## Change the data source for an element

You can also change the data source used for a specific element. For example, if you created a view in your Snowflake database and you want to update a Lifesight table element to use the view instead of the base table from the Snowflake connection, you can swap the source.

### Swap the data source for an element

After selecting an element in Edit or Explore mode, you can change the data source:

1. From the Dashboard canvas, select More > Element source > Change source. Or, at the bottom of the Element properties panel, locate the name of the data source and select  > Change source.
2. Search for or browse to a new data source for the element.
3. [optional] Preview the data source to choose specific columns, then click Add.
4. Select the data source to finish changing the data source.

The data element updates. If your element contains a calculated column that references a column that does not exist in the new data source, the calculated column displays an "unknown column".

### Replace the table used by a table element

If you want to replace the table used by a table or pivot table element with a different table, do the following:

1. From the Dashboard canvas, select  More > Element source > Replace table. Or, at the bottom of the  Element properties panel, locate the name of the data source and select  > Replace table.
2. Search for or browse to a new table for the element.
3. Review the selected columns and optionally deselect the checkboxes next to any unwanted columns.
4. Click Add.

The data element updates. If your table contains a calculated column that references a column that does not exist in the new table, the calculated column displays an "unknown column".