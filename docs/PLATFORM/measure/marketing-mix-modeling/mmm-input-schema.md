---
title: MMM input schema
excerpt: Schema to input all variables into your MMM model
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
High-quality input data is crucial for MMM to produce accurate and actionable results. Providing data in the appropriate format and with the right granularity ensures optimal performance.

<br />

![](https://files.readme.io/d15e7a89c00714626675b8156bc01292d9cb8d3d98e62465d36b4b0ecf035096-image.png)

<br />

## [MMM schema template](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1915444742#gid=1915444742)

**Mandatory Attributes for the MMM model**\
The header line of the input file must include attribute names, customizable according to business preferences. The essential attributes for MMM include:

* Date (yyyy-mm-dd)
* Dependent Variable  : Revenue, conversions, etc.
* Paid Media Variables :  TV spend, Google spend, etc.

<br />

<Table align={["left","left"]}>
  <thead>
    <tr>
      <th>
        Category
      </th>

      <th>
        Input variables
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Organic
      </td>

      <td>
        * Newsletters clicks/opens - Push notifications clicks/opens - Competitor marketing  - Product releases true/false - Price changes  - Social media posts click/impression - Content impression/reach
      </td>
    </tr>

    <tr>
      <td>
        Contextual
      </td>

      <td>
        * Marketing, Promotions, and PR - Advertising - Promotions - PR - Equity - Loyalty - Environmental, Seasonal, and Competition data
      </td>
    </tr>

    <tr>
      <td>
        Paid media
      </td>

      <td>
        * TV spend - Google spend and more - Offline spends
      </td>
    </tr>
  </tbody>
</Table>

***

<br />

## Data schema formatting & validation rules

* [ ] **Column Headers:** Must contain only alphanumeric characters and underscores, and must start with an alphabet.
* [ ] **Date Format:** Dates must be in the YYYY-MM-DD format.
* [ ] "**Date Frequency:** Dates can be daily, weekly, or monthly.\
  • Weekly Input: All dates must be either Sundays or Mondays (as the start of the week).
  • Monthly Input: All dates must be the first day of the month."
* [ ] **Consistent Data Granularity:** Ensure that the granularity (daily, weekly, monthly) is consistent throughout the dataset.
* [ ] **Data is rolled back to the past date.** For example all the data start from 1st Jan 2024 (which is a Monday) to 7th Jan 2024, should  be rolled back to 2024-01-01 (in case of weekly data)
* [ ] "**Data Range:** Ensure the data is atleast for 1 year in case of weekly data and daily data, Incase of monthly data the data should be atleast for 3 years.\
  Note : Recommended range of data should be for 2 years for weekly and daily."
* [ ] **Handling Missing Data:** Use appropriate techniques to handle missing data, such as interpolation or rolling averages. \[You can reach out to Lifesight Marketing Science team for any support here)
* [ ] "**Completeness:** There should be no missing dates in the data.\
  Example: For weekly data, each week must have a corresponding date."
* [ ] "**Missing Values:** If a channel was not used, populate its columns with 0. (There should be no NULL / Empty cells in the file)\
  Ex: If data provided is for 2 years but a channel was introduced only for the last 6 months then for the initial 1.5 years all the spend/impression/clicks should be updated with 0 as value."
* [ ] **Positive Integers Only:** All column values (e.g., spend, click, impression) must be positive integers.
* [ ] **Boolean Values:** Represent boolean columns (e.g., event indicators) with 1 for true and 0 for false.
* [ ] "**Numeric Values Only:** No non-numeric values are allowed, including empty spaces.\
  Example: Currency symbols are not needed for spend values."
* [ ] No Columns should have all Zero values. If it has then we should remove that column itself. For eg : When we pull data on a campaign/objective level for certain date range, We might get some columns with nothing to report.
* [ ] There should be proper format for the **Final Master file**, For eg: first column should contain date, second column should contain KPI(can be multiple KPI for two models) followed by all the base variables and lastly all the **Media variables**.
* [ ] It is recommended to delete all the unnecessary empty rows and columns from the master file before uploading into the platform
* [ ] Ensure that the number of independent variables to the number observations in rows should be of 1:4 range atleast.
* [ ] Make sure the list of independent variables is exhaustive in the Final Master file which involves incorportation all the types of data including Paid media vars, Organic vars, Seasonality vars, Contextual vars, Trends vars, Sales efforts vars and etc. which has any role in driving the KPI.