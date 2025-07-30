---
title: Input CSV Formatting Guidelines
excerpt: 'Data Validation & Formatting rules for CSV upload '
deprecated: false
hidden: true
metadata:
  robots: index
---
High-quality input data is crucial for MMM to produce accurate and actionable results. Providing data in the appropriate format and with the right granularity ensures optimal performance.

<br />

![](https://files.readme.io/d15e7a89c00714626675b8156bc01292d9cb8d3d98e62465d36b4b0ecf035096-image.png)

<br />

### [MMM CSV sample template](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1915444742#gid=1915444742)

**Mandatory Attributes for the MMM model**\
The header line of the input file must include attribute names, customizable according to business preferences. The essential attributes for MMM include:

* Date (yyyy-mm-dd)
* Output KPI: Revenue, Installs, conversions, etc.
* Paid Media Variables:  TV spend, Google spend, etc.

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
        Organic Variables
      </td>

      <td>
        * Newsletter Click Through Rate %
        * Push notifications Click Through Rate %

        - Social media posts Impressions & Engagement metrics
        - Blogs impressions
      </td>
    </tr>

    <tr>
      <td>
        Contextual Variables
      </td>

      <td>
        * Promotions, Loyalty, etc.

        - Environmental and Seasonal factors
        - Competitor activities - Product releases, price changes, promotions, etc.
      </td>
    </tr>

    <tr>
      <td>
        Paid media
      </td>

      <td>
        * Google Search Spends, Meta Retargeting spends, etc.
        * Linear TV spends, CTV Spends, etc.
        * Affiliate Spends, Influencer Spends, KOL Spends, etc.
        * Event Spends
      </td>
    </tr>
  </tbody>
</Table>

***

<br />

## File formatting & Data validation rules

* [ ] **Column Headers:** Must contain only alphanumeric characters and underscores, and must start with an alphabet.
* [ ] **Date Format:** Dates must be in the YYYY-MM-DD format.
* [ ] **Date Frequency:** Dates can be daily, weekly, or monthly.\
  • Weekly Input: All dates must be either Sundays or Mondays (as the start of the week).
  • Monthly Input: All dates must be the first day of the month."
* [ ] **Consistent Data Granularity:** Ensure that the granularity (daily, weekly, monthly) is consistent throughout the dataset.
* [ ] **Data is rolled back to the past date.** For example all the data start from 1st Jan 2024 (which is a Monday) to 7th Jan 2024, should  be rolled back to 2024-01-01 (in case of weekly data)
* [ ] **Data Range:** 2 years of historical data is recommended in case of weekly data and daily data. For monthly aggregation, 3 years of historical data is recommended.
* [ ] **Handling Missing Data:** Use appropriate techniques to handle missing data, such as interpolation or rolling averages. (Reach out to your dedicated Marketing Science team for support)
* [ ] **Completeness:** There should be no missing dates in the data.\
  Example: For weekly data, each week must have a corresponding date."
* [ ] **Missing Values:** If a channel was not used, populate its columns with 0. (There should be no NULL / Empty cells in the file)\
  Ex: If data provided is for 2 years but a channel was introduced only for the last 6 months then for the initial 1.5 years all the spend/impression/clicks should be updated with 0 as value."
* [ ] **Positive Integers Only:** All column values (e.g., spend, click, impression) must be positive integers.
* [ ] **Boolean Values:** Represent boolean columns (e.g., event indicators) with 1 for true and 0 for false.
* [ ] "**Numeric Values Only:** No non-numeric values are allowed, including empty spaces.\
  **Note:** Currency symbols are not needed for spend values."
* [ ] **Blanks Rows and Columns:**

  It is recommended to delete all the unnecessary empty rows and columns from the master file before uploading into the platform

  . No Columns should have all values populated as 0.
* [ ] **Consistent Data type:** The CSV file should be formatted uniformly with column headers in the first row and each column should contain values which are of the same data type.
* [ ] **Required Data-to-Feature Ratio:** Ensure that the number of independent variables columns to the number observations in rows is atleast of the ratio 1:4.
* [ ] **Comprehensive Data Inclusion:** Make sure the list of independent variables is exhaustive in the CSV file which involves incorporation all the types of data including Paid media variables, Organic variables, Seasonality variables, Contextual variables, Trend variables, etc. which has any role in driving the KPI.