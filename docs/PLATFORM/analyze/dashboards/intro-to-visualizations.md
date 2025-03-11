---
title: Visualizations
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Visualizations are graphical data elements that add visual context to your analysis. They allow you to create, explore, and view your data in a more focused and digestible format.

By adding visualizations to a Dashboard, you can reveal patterns, trends, outliers, and correlations crucial to creating a compelling data narrative. Build each visualization to deliver specific data insights and answer important questions that help you make better business decisions.

This document introduces the types of visualizations Lifesight offers and explains where to configure element properties and formatting.

## Visualization types

Effective visualizations are essential to telling meaningful data stories, but choosing the right types of visualizations can be a challenge. Consider the data type you want to visualize, the questions you need to answer, and the users who will view and consume your analysis.

The following information can help you choose visualizations for a clear and detailed narrative.

<Image align="left" width="200px" src="https://files.readme.io/198b2482933253d90deb9053f434b4ea862ef0e9ec74d701b70e0aa0923214af-bar-chart.png" />

### Bar chart

Show how values vary across categories or groups of data. Compare values against each other, to a reference mark, or as proportions of a whole.

<br />

<Image align="left" width="200px" src="https://files.readme.io/c54b09d9b0cbb31bfa5b5096a9bf41cad0c1e26c33e1c86bacd0573b19036f1a-line-chart.png" />

### Line chart

Show how the values of one or more metrics change over time. Spot trends and identify anomalies in your dataset.

<br />

<Image align="left" width="200px" src="https://files.readme.io/30fa2601202cc3848c00efe99299f7b9108ee0086d616a232e9e7b964374df8d-kpi-chart.png" />

### KPI chart

Highlight a single metric value to measure performance or progress toward a goal. Summarize the total value for a specific period, compare the value over time, or measure it against a benchmark or target.

<br />

<Image align="left" width="200px" src="https://files.readme.io/ba95bbeb64f3641e2812f7b9b5413617970ed638917cc4ff2e978ca48e853b2a-area-chart.png" />

### Area chart

Illustrate the magnitude or cumulative values of one or more metrics over time. Compare categories or groups of data, or evaluate the data composition or part-to-whole relationship.

<br />

<Image align="left" width="200px" src="https://files.readme.io/aab8dc4d1c616c95fa3c813d49d803a502159960d011bb249374e175de6b029b-scatter-plot.png" />

### Scatter plot

Demonstrate the presence and strength of a correlation between metrics. Analyze patterns, understand distribution, and identify outliers in your dataset.

<br />

<Image align="left" width="200px" src="https://files.readme.io/60fa2afef846d4c82cb33d0cd63197fa4fe5357ac048de0fd84dfd1020f66b0a-combo-chart.png" />

### Combo chart

Combine bar, line, area, and/or point marks to compare multiple types of metrics. Evaluate the relationship to identify correlations and variations between the datasets.

<br />

<Image align="left" width="200px" src="https://files.readme.io/a7115fc0e2e051208cf5a65e915169785535eaf72c7c2aaf355e7df1086eb662-box-chart.png" />

### Box chart

Show the value distribution of one or more metrics. Mark the minimum, median, and maximum values, and identify outliers in your dataset.

<br />

<Image align="left" width="200px" src="https://files.readme.io/84c59d0fb3644092f29a398710d7a7d6e3aed1ce70048c5a15c8fd057dd2a9b9-donut-chart.png" />

### Pie and Donut charts

Portray values as proportions of a whole to convey the data distribution and part-to-whole relationship.

<br />

<Image align="left" width="200px" src="https://files.readme.io/48d1359699f63e08ad5beeeac0c04d73c6c603c68818e1f71966150245e083ad-sankey-diagram.png" />

### Sankey diagram

Show how data flows and changes throughout a process or system. Compare the movements and proportions of data across different paths to analyze distributions, workflow, networks, and more.

<Image align="left" width="200px" src="https://files.readme.io/65a4245144d2ab3c3ba98c7a58247a5eb6e6ce0f2e37ad28af13f9e167bfe45c-funnel-chart.png" />

### Funnel chart

Measure values across sequential stages in a linear process. Gain insight into inputs across stages, identify bottlenecks and other issues, and assess the overall health of the process.

<Image align="left" width="200px" src="https://files.readme.io/0cd69a7c76eb0d90a9cbe77742ab449923115432be6dac353eb55b4651cba3b6-gauge-chart.png" />

### Gauge chart

Measure a single-value metric against a radial scale. Evaluate growth, assess performance, and track progress toward a goal.

<br />

<Image align="left" width="200px" src="https://files.readme.io/439528e63c7d19175c8107d0a05557c8ad5ae34093edec645c0ca55ff1d9f002-3ad246e-thumbnail-no-border.png" />

### Waterfall chart

Show changes in one or two categories of data over a time period.

<br />

<Image align="left" width="200px" src="https://files.readme.io/3c2a2fc00b70dc4ce2b76422327f8a9324eb02965471e5059a7fbeb128df2bfc-region-map.png" />

### Region map

Illustrate data distribution by region, including country, state, county, and city. Compare scale to identify variability and patterns across distinct geographical areas.

<br />

<Image align="left" width="200px" src="https://files.readme.io/566599936bc92960e038f265d7d2b31eaccd92e69be36bab8ab5ade9167f1e8b-point-map.png" />

### Point map

Illustrate data distribution with precise positioning based on latitude and longitude coordinates. Reveal geospatial patterns and identify outliers in your dataset.

<br />

<Image align="left" width="200px" src="https://files.readme.io/dde4d336c4138c2b06862b1bede65c8a439bae06da611cb5f401e98ec5f0a909-geography-map.png" />

### Geography map

Illustrate geospatial objects on a map using geography (WKT) or variant (GeoJSON) data. Demonstrate data distribution, reveal patterns, illustrate spatial networks, or assess data variability across distinct geographical areas.

<br />

## Custom configurations

Visualizations feature various properties and formatting options that determine how your data is represented. With a wide range of customizable configurations, you can enhance your visualizations and ensure they present meaningful and actionable information.

### Properties

The Element Properties panel requires selecting a visualization type and configuring source columns to define chart properties, including axis categories, metrics, colors, and tooltips.

You can convert data value types, change the data aggregation or truncation, and customize chart markers and tooltips. Depending on the visualization type selected, you may also have options to change the chart orientation, modify data stacking, and add trellis rows and columns.

<Image align="center" className="border" border={true} src="https://files.readme.io/4f7888933c15d9a9c9ebb29bd7acd694e23dc115a17a20ff2f2cd9e526fb970b-aad3c8f-1.png" />

```
                                                    _Element properties panel in Edit mode_
```

### Formatting

The  Element format panel allows you to customize the appearance of various components, including the visualization title’s content, size, and alignment. Depending on the visualization type selected, you may also be able to format the background, axes, legend, data labels, reference marks, trend lines, and more.

<Image align="center" src="https://files.readme.io/7b02071ca40dc414baf0ca81cc4535cce58664c61060c8f080228ccd04f07f93-7cd7232-2.png" />

```
                                                  _Element format panel in Edit model_
```

<br />

## Build a bar chart

Bar charts are typically used to compare values across categories or groups of data. Create basic single-series bar charts, or build advanced charts to compare multiple variables, measure values against reference marks, evaluate parts of a whole, and more.

This document details basic bar chart requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

> 📘 **Note**
>
> Use cases examples:
>
> * Store analytics: Measure total sales by product category to identify top and bottom-performing categories.
> * Marketing analytics: Track unique website page views by ad referral site (such as LinkedIn and GoogleAds) to understand ad performance trends and referral site effectiveness.
> * Accounting analytics: Monitor travel expenses by spend category to understand travel spend and identify categories that exceed expectations.
> * Education analytics (histogram): Count student exam results by score range to analyze frequency distribution and understand performance variability.

### User requirements

The ability to create bar charts and other visualizations requires the following:

1. You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
2. You must be the Dashboard owner or be granted Can explore or Can edit

### Basic bar chart requirements

To plot a bar chart, configure the following properties in the  Element properties tab:

**Chart**   Chart type displayed in the Dashboard\
**X-axis**  Source column that defines the x-axis (horizontal axis) categories or variable
**Y-axis**  Source column that defines the y-axis (vertical axis) categories or variable

In a bar chart, one axis typically represents ordinal or nominal categories (like stages, regions, and departments) presented as vertical or horizontal bars. The other axis represents a variable that measures a value (like sales, leads, expenses) for each category and determines the height or length of the corresponding bar. The type of data affiliated with each axis depends on the chart orientation, which you can modify at any time.

> 📘 **Note**
>
> At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a bar chart, Lifesight automatically calculates and structures the data to map the element properties to source columns in the underlying data table.

### Add a bar chart

Create a new visualization element and designate it as a bar chart.

1. Open a Dashboard in Explore or Edit mode and add a new visualization element.
2. In the Visualization property, click the dropdown field and select Bar from the list.

<Image align="center" width="500px" src="https://files.readme.io/bfec19a6f47b0def7d1c5ec75a25f4e7a55cc024b0e2ad4afc80a0be41f6aaa6-bar_visualization-type.png" />

<br />

### Define the categories

Configure a source column to define the chart categories.

When building a vertical bar chart (default orientation), apply the following steps to the X-axis property. When building a horizontal bar chart, apply the steps to the Y-axis property.

1. In the applicable axis property, click Add column and select an option from the menu:

   * To generate categories based on distinct values in an existing column, search or scroll the Select column list and select the preferred column name.
   * To generate categories based on a custom formula, select New column and enter the formula in the toolbar. For example, when building a histogram, create a custom formula using the BinRange or BinFixed function to generate categories based on value ranges.

   <Image align="center" width="700px" src="https://files.readme.io/322d2330320608aeb6a501f6a85ba8c52bb8ab04391c3d639f61069fd18d4db8-bar_define-categories_step-1.png" />
2. \`\[optional]\` Control how the source column data is categorized and displayed in the chart:
   * Hover over the source column name, then click the caret () to open the column menu.
   * Hover over any of the following items, then select the preferred option:
     * **Truncate date**	Categorize date values by the selected interval or unit of measure.
     * **Transform**	Convert the column to the selected data value type .
     * **Format**	         Display axis and data labels in the selected format.

> 📘 **Note**
>
> Availability of column menu items and corresponding options varies depending on the column’s data value type (for example, Truncate date is available for date values only).

### Define the variable

Configure a source column to define the chart variable. Lifesight automatically aggregates values associated with the same chart category.

Apply the following steps to the Y-axis property when building a vertical bar chart (default orientation) or the X-axis property when building a horizontal bar chart.

1. In the applicable axis property, click  Add calculation and select an option from the menu:
   * To aggregate values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
   * To calculate values based on a custom formula, select New column and enter the formula in the toolbar.
   * To count the number of rows associated with each category, select Row count.
2. \`\[optional]\` Control how the source column data is calculated and displayed in the chart:
   * Hover over the source column name, then click the caret to open the column menu.
   * Hover over any of the following items, then select the preferred option:
     * **Set aggregate**	Calculate values based on the selected aggregation method.
     * **Transform**	Convert the column to the selected data value type.
     * **Format** 	         Display axis and data labels in the selected format.
3. \`\[optional]\` Repeat the previous steps to add multiple y-axis source columns. Lifesight plots the columns as stacked or clustered series.
4. \`\[optional]\` Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:
   * To rename a source column, double-click the column name in the X-axis or Y-axis property, then enter a new name. Changes are reflected in the default chart title.
   * To edit the chart title, double-click the title in the visualization, then enter a new title.

### Advanced bar chart properties and formatting

Lifesight features various properties and format options that give you the flexibility to build advanced bar charts and variations, including stacked, percent stacked, clustered (grouped), and dual-axis bar charts.

The following sections introduce configurations that can enhance your bar charts and help you deliver specific insights with meaningful and actionable information.

### Change orientation and stacking

Change bar chart orientation and stacking in the  Element properties

> Visualization property to optimize the way you compare data across and within categories.

**Orientation**

* **Vertical** - Categorize data on the x-axis and measure values on the y-axis to create vertical bar marks.
* **Horizontal** - Categorize data on the y-axis and measure values on the x-axis to create horizontal bar marks.

**Stacking**

* **No stacking** - Plot multiple data series as separate bars within categories. Compare values across and within categories in the resulting clustered bar chart.
* **Stacked** - Plot multiple data series as cumulative bar segments. Compare subcategory contributions to each category’s total sum value in the resulting stacked bar chart.
* **Stacked 100%** - Plot multiple data series as stacked bars totaling 100% of each category’s total sum value. Compare subcategory distribution in the resulting percent stacked bar chart.

### Configure mark colors

You can configure the bar mark colors in the Element properties > Marks > Color tab to differentiate data, highlight specific values, use color to split bar values by category, or apply a color scale.

**Mark color**

* **Single color** - For each data series, enter a hex code or select an option from the color palette or color picker.
* **By category** - Select a source column to define color categories, then select or customize a color palette for the resulting stacks or clusters.
* **By scale** - Select a source column to define the color scale, then select a color range to apply to the marks.

> 📘 **Note**
>
> Multiple variables in the y-axis (in a vertical bar chart) or x-axis (in a horizontal bar chart) result in a stacked or clustered bar chart in which each data series represents a measure of a different variable. The **By category** color setting can also generate bar stacks or clusters, but the resulting series represent sub-categories (within the configured chart categories) that measure the same variable.

### Add conditional formatting

When you select Single color in the  Element properties

> Marks > Color tab, you can configure formatting rules (+ Add rule) that determine bar mark colors according to value-based conditions. This creates exceptions to the single-color selection, allowing you to highlight values that meet the specified conditions.

*Example*:

<Image align="left" width="300px" src="https://files.readme.io/c826ba5532c7058642da5d99f961863f0ca8ab868340df89bd4a4fad1ca97a3f-bar_marks_color_conditional-formatting.png" />

<Image align="center" width="400px" src="https://files.readme.io/8eb14f1d84a0fd5970c436f8b5ed6e0c51faa4f903f7a694b8fc86c7307932b5-bar_conditional-formatting.png" />

<br />

<br />

<br />

> 📘 **Note**
>
> When the conditions of multiple rules are met, Lifesight applies the formatting rules in order of precedence, from top to bottom. Drag and drop rule blocks to reorder them as needed.

### Customize tooltip fields and values

Customize chart mark tooltip fields in the Element properties

> Marks > Tooltip tab to display the most relevant metrics and data attributes. For more information, see Customize chart mark tooltip fields in this document.

When you apply chart stacking, you can also customize tooltips in the  Element format > Tooltip section to display the variable value as a percentage of the cumulative stack.

<Image align="left" width="400px" src="https://files.readme.io/9adb65b8daf5efe35c403e9c011524ce09cf15884f178d20bbdc5db012ebabea-bar_format_tooltip.png" />

<Image align="center" src="https://files.readme.io/f330a174259fd9e310b0f0a81a125d4a77ef465e99c975bc08406a8199ddb692-Screenshot_2025-01-30_at_10.49.40_AM.png" />

<br />

### Resize gap width

Resize gaps between bar marks in the Element format > Gaps section. Gap widths are auto-sized to optimize readability, but Lifesight gives you the flexibility to customize bar chart spacing.

<Image align="left" width="400px" src="https://files.readme.io/bef6075b476826beea98aa17f09f42030eac3364e23dd2f6173b8e0ddd7337dd-bar_format_gap-width.png" />

<br />

<br />

<Image align="center" src="https://files.readme.io/681b437240ddb05af7f24a0109278b87a49b27d9998a111abebf5aa05cb2e59b-Screenshot_2025-01-30_at_10.51.47_AM.png" />

## Build a line chart

Line charts are typically used to assess how values change over time. Create basic single-line charts to spot trends and identify anomalies in your dataset. You can also build advanced multi-line charts to analyze and compare multiple variables over the same period of time.

This document details basic line chart requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

<Image align="center" width="400px" src="https://files.readme.io/21ad974331dc9601c01fc9bfc3768fece161cf0b205a24c499b0db8bad8007a9-2915739-line-graph.png" />

<br />

> 📘 **Note**
>
> Use cases example:
>
> * Consumer packaged goods (CPG) analytics: Compare monthly profit margins by product category to understand profit trends and gain insight into overall business profitability.
> * Manufacturing analytics: Track machine uptime percentage by the hour to identify productivity lapses and reliability issues.
> * Air travel analytics: Assess monthly percentage of on-time flight departures by airline to understand seasonal patterns and compare operational efficiency across companies.

### User Requirements

The ability to create line charts and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

### Dashboard prerequisite

Before you can build a line chart, you must add a new visualization element and select a data source.

At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. Lifesight automatically groups, aggregates, and calculates the underlying data to create source columns for various visualization properties as you build a line chart. You can view the underlying data table while configuring the chart to see how the data is applied.

> 📘 **Note**
>
> Line charts support up to 25,000 data points. If the configurations result in a data set that exceeds this limit, the chart displays the first 25,000 data points, and a warning message indicates that the chart is incomplete. To reduce the number of data points, aggregate the values or apply data filters to the visualization or source element.

### Basic line chart requirements

To plot a line chart, configure the following properties in the Element properties panel:

**Chart**   Chart type displayed in the Dashboard\
**X-axis**  Source column that defines the x-axis (horizontal axis) categories
**Y-axis**  Source column that defines the y-axis (vertical axis) variable

In a line chart, the x-axis typically represents time-based categories (like dates, months, years) that correspond with individual data points. The y-axis represents a variable that measures a value (like sales, leads, expenses) for each category and determines the vertical placement of each data point.

### Select the visualization type

Once you add a new visualization to a Dashboard, select the visualization type:

* In the Visualization property, click the dropdown field and select Line from the list.

<Image align="center" width="400px" src="https://files.readme.io/227169b22640dcc45657a1bea3501d7a2344e62e6e2c0d325c9d2e3ed85e6ddc-a4c77f1-line_visualization-type.png" />

<br />

### Define the x-axis categories

Configure a source column to define the x-axis categories.

1. In the X-axis property, click Add column and select an option from the menu:

* To generate categories based on distinct values in an existing column, search or scroll the Select column list and select the preferred column name.
* To generate categories based on a custom formula, select New column and enter the formula in the toolbar.

2. \`\[optional]\` Control how the source column data is categorized and displayed in the chart:

* Hover over the source column name, then click the caret () to open the column menu.
* Hover over any of the following items, then select the preferred option:
  * **Truncate date**  Categorize date values by the selected interval or unit of measure.
  * **Transform**        Convert the column to the selected data value type.
  * **Format**              Display axis and data labels in the selected format.

### Define the y-axis variable

Configure a source column to define the y-axis variable. Lifesight automatically aggregates values associated with the same x-axis category.

1. In the Y-axis property, click Add calculation and select an option from the menu:

* To aggregate values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
* To calculate values based on a custom formula, select New column and enter the formula in the toolbar.
* To count the number of rows associated with each category, select Row count.

> 📘 **Note**
>
> You can also select an existing column by dragging and dropping a column name from the Columns list to the Y-axis property.

2. \`\[optional]\` Control how the source column data is calculated and displayed in the chart:

* Hover over the source column name, then click the caret () to open the column menu.
* Hover over any of the following items, then select the preferred option:
  * **Set aggregate**  Calculate values based on the selected aggregation method.
  * **Transform**         Convert the column to the selected data value type.
  * **Format**               Display axis and data labels in the selected format.

> 📘 **Note**
>
> To plot the source column data without aggregating values, clear the Aggregate values checkbox in the Y-axis property. If this results in an incomplete chart that exceeds the 25,000 data point limit, reaggregate the values or apply data filters to reduce the number of data points.

<br />

3. \`\[optional]\` Repeat the previous steps to configure multiple y-axis source columns. Lifesight plots each as a separate line series on the chart.
4. \`\[optional]\` Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:

* To rename a source column, double-click the column name in the X-axis or Y-axis property, then enter a new name. Changes are reflected in the default chart title.
* To edit the chart title, double-click the title in the visualization, then enter a new title.

> 📘 **Note**
>
> Lifesight auto-generates the default chart title only. Once the title is customized, it no longer reflects changes to source columns and their names.

### Advanced line chart properties

Lifesight features various properties and format options that give you the flexibility to build advanced line charts and variations, including multi-line, step-line, and dual-axis line charts.

The following sections introduce configurations that can enhance your line charts and help you deliver specific insights with meaningful and actionable information.

**Configure mark colors**

Configure line mark colors in the Element properties

> Marks > Color tab to differentiate data, highlight associations, or add a color category.

<Image align="left" width="400px" src="https://files.readme.io/6e7c16fda1e9765035d4b8570877ccb8e22ce03cf829b5a2ee5f1627bc026ccf-6f4f6ed-line_marks_color.png" />

<Image align="center" src="https://files.readme.io/7e5d7ec5af5014f4048ea0a9f90fc705999621e94d567358178b45d419e1aeca-Screenshot_2025-01-30_at_11.19.15_AM.png" />

> 📘 **Note**
>
> Multiple variables in the y-axis result in a multi-line chart in which each data series represents a measure of a different variable. The By category color setting can also generate a multi-line chart, but the resulting series represent sub-categories (within the x-axis categories) that measure the same variable.

### Customize line style

Customize line styles in the  Element format

> Line Style section. When the line chart contains multiple y-axis variables, you can modify the different data series individually or together.

<Image align="left" width="300px" src="https://files.readme.io/a4b3b4452ce8b0055d356968daf4d30be52f076b24da0f9066d109b4b864c5dd-dfe5197-line_format_line-style.png" />

<br />

<br />

<br />

<br />

<br />

In addition to customizing the line pattern (solid, dashed, or dotted) and weight (1-5px), you can choose the type of interpolation path:

<Image align="left" src="https://files.readme.io/45f8d40bf9dceaf344ee05f8e489ae700050ceccc9c7514352f104050bd25416-Screenshot_2025-01-30_at_11.21.51_AM.png" />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

You can also show or hide individual data points and control how the line chart handles null values:

<Image align="center" src="https://files.readme.io/648e537d85488b652b7194c9dce629366f42e851bb8495bde4632d6476516dcb-Screenshot_2025-01-30_at_11.23.29_AM.png" />

By default, line charts hide distinct data points between line connections. If you select the Show points checkbox, you can display the points and customize their size (2-15px) and shape:

<Image align="center" src="https://files.readme.io/9c84b70d3515d61f344c8108d4cfe612d417f8c23c71a8108dbecfb80b73ed24-Screenshot_2025-01-30_at_11.24.34_AM.png" />

## Build a KPI chart

> 📘 **Note**
>
> Lifesight's KPI visualization element has replaced the Single Value visualization (SVV) option.

Key performance indicator (KPI) charts highlight single metric values typically used to measure performance or progress toward goals. Create a KPI chart to summarize the total value of a metric for a specific period, or include additional data to compare the metric’s value over time and measure it against a benchmark or target value.

<Image align="center" src="https://files.readme.io/b96f85ff9b7c2faa59626c38e1b470e251caa85da3ae067b35c912edf864dde5-kpi-chart_intro.png" />

> 📘 **Note**
>
> Use cases example:
>
> * Marketing analytics: Track click-through rates to highlight email campaign performance over time.
> * Executive Dashboarding: Measure monthly year-over-year revenue to understand how the current month’s revenue compares to the previous year benchmark.
> * Manufacturing analytics: Report cycle time to analyze the amount of time it takes a product to complete the manufacturing process.

### User requirements

The ability to create KPI charts and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

> 📘 **Note**
>
> If you’re granted Can explore access to the Dashboard, you can create and modify visualization properties and formatting in Explore mode, but you cannot publish your changes.

### KPI chart variations

Lifesight’s KPI charts allow you to track and display metrics in various ways depending on how you configure the element properties.

**Static variations**

<Image align="left" width="400px" src="https://files.readme.io/8ecc993e4f860cd2babb7987e12d4cdf6d28d3826a8a9b229212e66209a9fdc9-kpi_chart-variations_summary-value.png" />

**Summary value**\
Summarize the metric's global value to understand overall performance or magnitude.

The KPI chart highlights the global summary, which aggregates the metric values across the entire dataset.

Required element properties:\
Value

<br />

<Image align="left" width="400px" src="https://files.readme.io/ea621d40abfc8a7b8642aef65f6a2773a2fe2259ed5ef733e1c6ec3b2e6695ff-kpi_chart-variations_summary-value-comparison.png" />

**Benchmark summary comparison**\
Summarize a metric's global value against a benchmark or target value. Assess relative performance and gain insight into patterns, relationships, and correlations.

The KPI chart highlights the global summary, which aggregates the metric values across the entire dataset. It also displays a comparison as a percentage, delta, or absolute value.

<br />

Required element properties:\
Value
Comparison (Column)

**Time series variations**

<Image align="left" width="400px" src="https://files.readme.io/94c31b637b7157bab8c6f3692d1120c1ac491c6d6c00335fc72be61132d6f492-kpi_chart-variations_period-value.png" />

**Period value**\
Measure a metric's period value to analyze performance during a specific time interval (like week, month, or year).

The KPI chart highlights the latest period value or global summary, and it can display a trend line that illustrates patterns and changes across sequential time periods.

<br />

<br />

Required element properties:\
Value
Timeline

<Image align="left" width="400px" src="https://files.readme.io/3be0b513100b1fb6a67817411d2cf1413e2fd9f8f82fe2c3880a1534f329dfda-kpi_chart-variations_period-comparison.png" />

**Period comparison**\
Measure a metric’s value in one period (like week, month, or year) against another to perform a sequential or period-over-period comparison.

The KPI chart highlights the latest period value or global summary, and it can display the comparison as a percentage, delta, or absolute value. It can also include a trend line that illustrates patterns and changes over time.

Required element properties:\
Value
Timeline
Comparison (Period)

<Image align="left" width="400px" src="https://files.readme.io/48b4c2ee5e3b86f4ae1b2fe54296dadd9c2478e91e1b0984102e3aa354c956ee-kpi_chart-variations_period-value-comparison.png" />

**Benchmark period comparison**\
Compare a metric's period value against a benchmark or target to assess relative performance and gain insight into patterns, relationships, and correlations.

The KPI chart highlights the latest period value or global summary, and it can display a comparison as a percentage, delta, or absolute value. It can also include a trend line for both values to illustrate patterns and changes over time.

Required element properties:\
Value
Timeline
Comparison (Column)

> 📘 **Note**
>
> When loading or refreshing a Dashboard, Lifesight typically sends a separate query for each data element. If the Dashboard contains multiple static KPI charts (summary value and benchmark summary comparison variations) that share a data source, Lifesight employs query batching. This consolidates the data requests from all applicable KPI charts into a single query to reduce query processing overhead and optimize performance. Time series KPI charts (period value, period comparison, and benchmark period comparison variations) send separate queries to the database and aren't included in query batching.

### Basic KPI chart configurations

Build a basic KPI chart by configuring the following element properties:

* **Chart**             Chart type displayed in the Dashboard
* **Value**             Calculation that determines the metric value
* **Timeline**        Date data that defines the reporting period
* **Comparison**  Period or calculation that defines the comparison value

> 📘 **Note**
>
> At the core of every visualization element is its underlying data, which supplies the information the chart visualizes. As you build a KPI chart, Lifesight automatically calculates and structures your data to associate element properties with columns ("source columns") in the underlying data table.
>
> When you configure a property by aggregating an existing column, adding a custom formula or value, or applying the row count, Lifesight creates a new source column.\
> For information about how to view the underlying data while you configure the chart, see Maximize or minimize a data element.

### Add a KPI chart element

Create a visualization element and designate it as a KPI chart.

> 📘 **Note**
>
> You can also create a new KPI chart directly from a summary value in a table element. Right-click the table summary to open the menu, then select Create KPI element.

1. Open a Dashboard in Explore or Edit mode and add a new visualization element.
2. In the Visualization property, click the dropdown field and select KPI from the list.

<Image align="center" width="450px" src="https://files.readme.io/e6bfe7e17f489fe2e9dedb4839fd92a154aa60d49ba6e4394b5aafd953729dfb-kpi_visualization-type.png" />

### Calculate the metric

Configure the Value property to calculate the metric. This configuration is required to build any KPI chart variation.

1. In the Value property, click  Add calculation, then use one of the following methods to calculate the metric:

* To aggregate the values of an existing column, search or scroll the Aggregate column list and select the preferred column.
* To add a custom calculation or value, select Add new column, then enter the calculation or value in the formula bar.
* To count the number of rows in the underlying dataset, select Row count.

<Image align="center" width="450px" src="https://files.readme.io/166fb0995ce0f06ed6094da9804431674f618fb30da77271c884458dce0930f7-kpi_define-metric-value_step-1a.png" />

When the Timeline property is not configured, the chart displays the metric's global summary value, which aggregates all data points in the resulting Value property source column. If you deselect the Aggregate values checkbox, one value from the column is selected and displayed instead of a global summary.

<Image align="center" width="450px" src="https://files.readme.io/e444241b6f838d33c3d3c7b1a01f5bdfdf26c05c3c16c20e483c7922b7597974-kpi_define-metric-value_step-1b.png" />

When you add a metric, the values are automatically aggregated and the Aggregate values checkbox is selected

2. \`\[optional]\` If you want to control how the metric is measured and formatted, leave the Aggregate values checkbox selected and adjust the aggregate, data type, or format of the metric value using the column menu or formula toolbar:
   * In the Value property, hover over the column name, then click the caret () to open the column menu.
   * Hover over any of the following items and select the preferred option:

* **Set aggregate**  Measure the metric based on the selected aggregation method.
* **Transform**         Convert the column to the selected data value type.
* **Format**               Display the metric value in the selected format.

For example, you can format a sum of profit KPI to display using SI units:

<Image align="center" width="450px" src="https://files.readme.io/612d284beb624181e408f9728e95dfb867a28f8fa871aee0feb68af39f7127e2-kpi_define-metric-value_step-2a.png" />

<Image align="center" width="450px" src="https://files.readme.io/cb633e4b7f53632df1be5cba401841bf2c4776318a24a6f9bcc83b1f912c023e-kpi_define-metric-value_step-2b.png" />

### Define the reporting period

Configure the Timeline property to define the reporting period for the time series. This configuration is required to build a period value, period comparison, or benchmark period comparison KPI chart.

1. In the Timeline property, click  Add column, then use one of the following methods to define the reporting period:

* To derive the period from an existing date column, search or scroll the Select column list and select the preferred column.
* To create a period based on a new date column, select Add new column, then enter a date function or value in the formula bar.

> 📘 **Note**
>
> The Timeline property supports date columns only. You cannot select or create a column that does not contain date data.

<Image align="center" width="450px" src="https://files.readme.io/5c77af915bfeb169ed2c1b8f432970e5e32ae97cdc0945442acd2be9bb7abef0-kpi_define-measurable-period_step-1a.png" />

When a source column is added to the Timeline property, two changes occur in the chart:

* The chart now displays the metric's latest period value, which aggregates the Value property source column data for the most recent period. To change the default display value to the global summary, proceed to the next step.
* If the element layout size allows, the chart displays a trend line, which you can hover over to view previous period values.

<Image align="center" width="450px" src="https://files.readme.io/a2ee1ca657e378e9d6d2f666e52c2cd9d372a16b2912c79c856441220e56530b-kpi_define-measurable-period_step-1b.png" />

2. \`\[optional]\` Change the default display type (the value displayed when not interacting with the trend line):

* In the Value property, hover over the source column name, then click the caret () to open the column menu.
* Hover over Default display type and select an option:

  * **Latest period**       Display the aggregate value for the most recent period in the time series.
  * **Global summary**  Display the aggregate value for all periods in the time series.

  <Image align="center" width="450px" src="https://files.readme.io/570141eecf83606effe8ecf6bb555ce33faf4c5423596fdfda56a1c8147565ee-kpi_define-period_change-default-display-type.png" />

3. \`\[optional]\` Control how the period is measured and formatted:

* In the Timeline property, hover over the column name, then click the caret () to open the column menu.
* Hover over any of the following items and select the preferred option:
  * **Truncate date**    Measure the metric value based on the selected period.
  * **Format**                Display the period date in the selected format.

<Image align="center" width="450px" src="https://files.readme.io/1016dffa7485d729e3e3dc0cdd883e62ad276bb3547cc3558dfdea9f73a7b22a-kpi_define-measurable-period_step-2.png" />

### Select a comparison period

Configure the Comparison > Period property to measure a sequential or period-over-period comparison for the metric. This configuration is required to build a period comparison KPI chart.

When the benchmark or target value is null (for example, the first week in a sequential week-over-week analysis), the comparison value and label are hidden.

1. In the Comparison property, enable the Period option. If a source column is configured in the Timeline property, the option is automatically enabled.
2. Open the dropdown and select a type of period comparison.

> 📘 **Note**
>
> Configuring a column in the Timeline property automatically engages the Comparison property. To build a KPI chart that highlights the period value of a metric without displaying a comparison, ensure the dropdown is set to None.

<Image align="center" width="450px" src="https://files.readme.io/94fad8e1c28ad387b16de2700cf91d9f8b4465f1542ef074fe1b4e9ca56949ac-kpi_define-comparison-period_step-2a.png" />

By default, a comparison value displays as a percentage. To instead display a delta or absolute value, customize the comparison in the Element format panel.

### Select a comparison value

Configure the Comparison > Column property to measure the metric against a benchmark or target value. This configuration is required to build a benchmark summary comparison or benchmark period comparison KPI chart.

1. In the Comparison property, click  Add calculation, then use one of the following methods to calculate the benchmark or target value:

* To aggregate values in an existing column, search or scroll the Aggregate column list and select the preferred column.
* To add a custom calculation or value, select Add new column, then enter the calculation or value in the formula bar.
* To count the number of rows in the underlying dataset, select Row count.

<Image align="center" width="450px" src="https://files.readme.io/0c75ed3df0a6b9a3a3e9b0a939913794e040c1618d1aaebdd9b87917a6e07877-kpi_define-comparison-value_step-2a.png" />

By default, a comparison value displays as a percentage. To instead display a delta or absolute value, customize the comparison in the Element format panel.

2. \`\[optional]\` Control how the benchmark or goal is measured and formatted:

* In the Comparison property, hover over the column name, then click the caret () to open the column menu.
* Hover over any of the following items and select the preferred option:

  * **Set aggregate**     Measure the metric based on the selected aggregation method.
  * **Transform**            Convert the column to the selected data value type.

  <Image align="center" width="450px" src="https://files.readme.io/0c139ef5f82550a663c26a1a02e8efc774d2e2043fd53d02c0b4ee017a5e3385-kpi_define-comparison-value_step-3.png" />

<br />

### Advanced KPI chart properties and formatting

Lifesight features various properties and format options that give you the flexibility to build detailed KPI charts.

The following sections introduce configurations that can enhance your charts and help you deliver specific insights with meaningful and actionable information.

### Change the value color

Change the metric value’s font color in the  Element properties > Marks > Color tab. This determines the default color of the metric value, which can be overridden by conditional formatting rules.

> 📘 **Note**
>
> The Color property (including conditional formatting) applies to the metric value only and doesn’t affect the element title or comparison font.

<Image align="left" src="https://files.readme.io/9ea1d100491d87d725e55bff54cdeaa1f5613be56ac1b8bd7528f2cf8ba31181-kpi_properties_marks_color.png" />

<Image align="center" width="300px" src="https://files.readme.io/623903e1870db02b53c516b3a81f4f766189632f9f63e3c3a581d3bb90169c52-kpi_marks_color.png" />

<br />

### Add conditional formatting

Configure formatting rules rules (click + Add rule) in the  Element properties > Marks > Color tab to change the metric value’s font color according to value-based conditions. This allows you to highlight or emphasize the value when it meets the specified conditions.

### Customize the value font

Customize the metric value’s font weight, color, and size in the  Element format > Value section.

> 📘 **Note**
>
> The Value format settings apply to the metric value only and don’t affect the element title or comparison font. If you change the font color in this section, the font color is also changed in the element’s Color property.

<Image align="center" src="https://files.readme.io/37153d9a20617383321c6780829fe654b2ef76f6c431f8b519cf487c94736b2c-kpi_format_value.png" />

<br />

### Customize the comparison display

Customize the comparison display in the  **Element format > Comparison section.**

<Image align="center" src="https://files.readme.io/7bed6bad332f27b0923bb3b848df8ffe800206f9d5c6e214c4133ea29192c268-kpi_format_comparison.png" />

<Image align="center" src="https://files.readme.io/af258895364531dc903e6d772e354d45fe7e15b64e0b90e9464683d573297d30-kpi_format_comparison.png" />

<br />

In addition to modifying the color indicators, you can change the font size of the comparison value, show or hide the label, and customize the label content.

You can also select the type of comparison displayed and identify the favorable direction of the comparison. The Direction setting determines when the Good color, Neutral color, and Bad color indicators apply to the comparison value.

<Image align="center" src="https://files.readme.io/34f25a9c6fec88c90ab3b30c4214b290bb6cf64e82d0e842cead6b9d4e63964b-Screenshot_2025-03-05_at_5.11.26_PM.png" />

<Image align="center" src="https://files.readme.io/aea143bebe0ae3e8ec6b50061f08afd43d1282c76769d877a218e26abe35f1cf-Screenshot_2025-03-10_at_10.49.07_AM.png" />

### Customize the trend line

Customize the trend line in the  Element format > Trend section.

<Image align="center" src="https://files.readme.io/f369ed0801946b205d2f7e10432a6820b2ba88a3672262a1e62f8aa813df4453-kpi_format_trend.png" />

In addition to showing and hiding the trend line, you can select the trend line shape (line or area) and customize its colors.

<Image align="center" src="https://files.readme.io/bba83be4d63e4f670b9622ab35bcfb9cf07f4ad3049575ffc55cc61302b37442-Screenshot_2025-03-10_at_11.17.11_AM.png" />

You can also enable tooltips on hover, display the x-axis with timeline tick marks and labels, and display the y-axis with grid lines and labels.

<Image align="center" src="https://files.readme.io/081c02eceef7c23be3cd9970f5423c76b1083c814bbb2d42e852c149de4135c2-Screenshot_2025-03-10_at_11.17.53_AM.png" />

### Customize the chart layout

Customize the chart layout in the  Element format > Layout section.

<Image align="center" src="https://files.readme.io/dcd9c56ccbd12d2fd40337a8511466477803fc87aece6f2aed646823228c1e2e-kpi_format_layout.png" />

Change the alignment of the text components, and select the location of the title and comparison value.

<Image align="center" src="https://files.readme.io/7851c41f95e6f328e0b1a84a4c949594ceec46f936578e1dbce8145bfec7b67a-Screenshot_2025-03-10_at_11.19.38_AM.png" />

<Image align="center" src="https://files.readme.io/f89d38f41a01bbfa9f69ed53ff6b30db9abd869e2cf0e721974189982e77e0b7-Screenshot_2025-03-10_at_11.20.08_AM.png" />

## Build a scatter plot

Scatter plots are typically used to demonstrate a correlation (or lack thereof) between two different variables. Create basic scatter plots to assess patterns, trends, and outliers in your dataset. You can also build advanced charts to include additional variables, plot trend lines, and display data points across quadrants.

This document details basic scatter plot requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

<Image align="center" width="450px" src="https://files.readme.io/16334d95cf1f60c758c2b667abf02e6e2202a3b928c28f29d856c20e922b79ff-4a3a572-1.png" />

> 📘 Example use cases:
>
> Education analytics: Assess college grades and post-college income to determine a possible correlation between academic performance and job earnings.
>
> Environmental health analytics: Compare metro health index scores by neighborhood air pollution amount to analyze patterns and identify areas needing intervention.
>
> Retail analytics: Track price changes and sales amounts by profit to understand consumer response to price changes and identify where pricing did not affect profit.

### User requirements

The ability to create scatter plots and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

### Dashboard prerequisite

Before you can build a scatter plot, you must add a new visualization element and select a data source.

At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a scatter plot, Lifesight automatically groups, aggregates, and calculates the underlying data to create source columns for various visualization properties. You can view the underlying data table while configuring the chart to see how the data is applied.

> 📘 Scatter plots support up to 25,000 data points. If the configurations result in a data set that exceeds this limit, the chart displays the first 25,000 data points, and a warning message indicates that the chart is incomplete. To reduce the number of data points, aggregate the values or apply data filters to the visualization or source element.

### Basic scatter plot requirements

To display a scatter plot, configure the following properties in the Element properties tab:

* Visualization - chart type displayed in the Dashboard
* X-axis - source column that defines the x-axis (horizontal axis) variable
* Y-axis - source column that defines the y-axis (vertical axis) variable

In a scatter plot, data points express the intersection of different variables on the x- and y-axis (like revenue and COGS, temperature and precipitation, page views and clicks).

### Select the visualization type

Once you add a new visualization to a Dashboard, select the visualization type:

* In the Visualization property, click the dropdown field and select Scatter from the list.

<Image align="center" src="https://files.readme.io/af3fb57db1ed0c4c2fb79bf104f28439ce5ed41afdf8057539ef2aaffbb9b97f-d78616a-2.png" />

> 📘 You can also use this dropdown field to convert an existing visualization to a different type. Lifesight retains all property and format configurations shared by the initial and new type. Unshared properties and formatting are not saved or restored if you further convert the visualization.

### Define the x-axis variable

Configure a source column to define the x-axis variable.

1. In the X-axis property, click + Add column and select an option from the menu:

* To plot values from an existing column, search or scroll the Select column list and select the preferred column name.
* To plot values based on a custom formula, select New column and enter a formula in the toolbar.

<Image align="center" src="https://files.readme.io/6f959326d80344cc5ca19feb3546e065e47297e73ff94bae331e6d2c2ed24496-11bb699-3.png" />

2. \[optional] Control how the source column data is grouped and displayed in the chart:

* Hover over the source column name, then click the caret () to open the column menu.
* Hover over any of the following items, then select the preferred option
  * Truncate date - Group date values by the selected interval or unit of measure.
  * Transform - Convert the column to the selected data value type.
  * Format - Display axis and data labels in the selected format.
  > 📘 Availability of column menu items and corresponding options varies depending on the column’s data value type (for example, Truncate date is available for date values only).

<Image align="center" src="https://files.readme.io/5b34b38b5056a721f61b677737d6138ab0726808a88033b6efa438fa573e54fc-046b373-4.png" />

### Define the y-axis variable

Configure a source column to define the y-axis variable. Lifesight aggregates y-axis values that correlate with the same x-axis value.

1. In the Y-axis property, click + Add calculation and select an option from the menu:

* To aggregate values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
* To calculate values based on a custom formula, select New column and enter the formula in the toolbar.
* To count the number of rows associated with each category, select Row count.

<Image align="center" src="https://files.readme.io/189e67cce56027699a2b8b90613c4c9615fac3dd12db1d79cbe33a492d8c266f-22cff53-5.png" />

2. \[optional] Control how the source column data is calculated and displayed in the chart:

* Hover over the source column name, then click the caret () to open the column menu.
* Hover over any of the following items, then select the preferred option:
  * Set aggregate - Calculate values based on the selected aggregation method.
  * Transform - Convert the column to the selected data value type.
  * Format - Display axis and data labels in the selected format.
  > 📘 To plot the source column data without aggregating values, clear the Aggregate values checkbox in the Y-axis property. If this results in an incomplete chart that exceeds the 25,000 data point limit, reaggregate the values or apply data filters to reduce the number of data points.

<Image align="center" src="https://files.readme.io/a8d211f9d3fa88628689b1e9235b0c70c37ee8bdcebd7a5c24b609aa2744b045-cdb77a6-6.png" />

3. \[optional] Repeat the previous steps to add multiple y-axis source columns. Lifesight plots each as a separate point series on the chart.

<Image align="center" src="https://files.readme.io/48a38559c32a943af89a718f91dbc4e42bbfafd2116b64c6087865d0ac207541-62915fa-7.png" />

4. \[optional] Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:
   * To rename a source column, double-click the column name in the X-axis or Y-axis property, then enter a new name. Changes are reflected in the default chart title.
   * To edit the chart title, double-click the title in the visualization, then enter a new title.

### Advanced scatter plot properties and formatting

Lifesight features various properties and format options that give you the flexibility to build advanced scatter plots and variations, including bubble charts and quadrant charts.

The following sections introduce configurations that can enhance your scatter plots and help you deliver specific insights with meaningful and actionable information.

### Configure mark colors

Configure point mark colors in the Element properties > Marks > Color tab to differentiate data, add a color category, or create a color scale.

<Image align="center" width="300px" src="https://files.readme.io/aa761672ef2d30e26bf3bf55a8342c50010c90ac446739076baf1c5292a67611-ba82973-9.png" />

<Image align="center" src="https://files.readme.io/04afa1690df0245715f37ea4c6b434da3e900742e889a57a53c3b3d0e7956b21-Screenshot_2025-03-10_at_12.05.39_PM.png" />

> 📘 Multiple variables in the y-axis result in a multi-series scatter plot in which each data series represents a measure of a different variable. The By category color setting can also generate a multi-series scatter plot, but the resulting series represent sub-categories that measure the same variable.
>
> 💡As with axis variables, you can control how color category and color scale source column data is calculated and displayed in the chart.

### Add conditional formatting

When you select Single color in the Element properties > Marks > Color tab, you can configure formatting rules (+ Add rule) that determine point mark colors according to value-based conditions. This creates exceptions to the single-color selection, allowing you to highlight values that meet the specified conditions.

<Image align="left" src="https://files.readme.io/70fe2bf7cc7f10539126862c986c01761db718285728749eb75421a7f39ebbe7-37515e1-10.png" />

<br />

<br />

<br />

<br />

<br />

Example:

<Image align="center" src="https://files.readme.io/d5ead4e93088d2501cf320d1351dde5fb2760c4058ca6c72edac58074fc11edd-Screenshot_2025-03-10_at_12.08.09_PM.png" />

### Configure mark size

Configure point mark size in the  Element properties > Marks > Size tab to add a size variable and create a bubble chart.

<Image align="center" src="https://files.readme.io/08af2a73436e173c420a8f1e0fd70b15eef7f079f8e0dd2bd6d9f4df4ae8c439-b372aa7-11.png" />

Select a source column to define the size variable. Lifesight aggregates values that correlate with the same x-axis value, then proportions the points based on an auto-generated size range. To modify the relative sizing, see Customize Point Style below.

<Image align="center" src="https://files.readme.io/98259c6b106ef78f100f46070ed755dbd2be95782da40a939d65fbe196d7d3de-5883395-12.png" />

> 📘 As with the axis variables, you can control how the size variable source column data is calculated and displayed in the chart.

### Customize point style

Customize point styles in the  Element format > Point style section. When the scatter plot contains multiple y-axis variables, you can modify the different data series individually or together.

<Image align="center" src="https://files.readme.io/2b2e4cf12e433be4c920b8f4b0f0b61be7c8f6afecbc2339560532a72626ae00-c5e565b-13.png" />

By default, scatter plot points are circular. You can change the point shape to differentiate multiple data series:

<Image align="center" src="https://files.readme.io/04ab36fcd9988f462c2b10f53c768c5b1fcd6fecb57d260723fcbf35eaf4c256-Screenshot_2025-03-10_at_12.12.59_PM.png" />

If the chart doesn’t include a size variable, you can customize the point size in pixels (2-15px) to optimize readability. Otherwise, you can apply relative sizing to change the minimum point size in the range:

<Image align="center" src="https://files.readme.io/8fc00b20b6577c16d736b18b9664cf2c9d8d9a4660fb29119b2d42e62a40fb1a-Screenshot_2025-03-10_at_12.13.42_PM.png" />

### Add reference marks

Add reference marks in the Element format > Reference marks section to demarcate goals, baselines, or other benchmarks. With scatter plots, you can also use reference marks to create quadrant charts.

<Image align="center" src="https://files.readme.io/d1e97cf4a537759aa39da2cb1441501815b327888f83f6cada0293945c5fa008-11b8678-14.png" />

<Image align="center" src="https://files.readme.io/28c297edec5ab46ebcc9da6434f46f1a41b04804c0a1ddf997a149f64fb43a51-Screenshot_2025-03-10_at_12.14.58_PM.png" />

## Build a Sankey diagram

Sankey diagrams are typically used to assess the flow and change of data between stages in a process or system. Create simple Sankey diagrams to demonstrate data distribution, workflows, networks, and more, or build advanced multi-level diagrams to analyze complex data relationships and identify changes in variables across stages, categories, or periods.

This document details basic Sankey diagram requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

> 📘 Example use cases:
>
> * Energy analytics: Measure electricity load and consumption to understand facility performance and gain insight into the origins and transformation of energy.
> * Financial analytics: Track annual spend by department, division, and expense category to understand the flow of money and analyze budget vs. spend distribution.
> * Marketing analytics: Follow website visitor activity by parent domain and subsequent page visits to understand user navigation and assess website architecture deficiencies.

### User requirements

The ability to create Sankey diagrams and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

### Dashboard prerequisite

Before you can build a Sankey diagram, you must add a new visualization element and select a data source.

At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a Sankey diagram, Lifesight automatically groups, aggregates, and calculates the underlying data to create source columns for various visualization properties. You can view the underlying data table while configuring the chart to see how the data is applied.

> 📘 Sankey diagrams support up to 25,000 data points. If the configurations result in a data set that exceeds this limit, the chart displays the first 25,000 data points, and a warning message indicates that the chart is incomplete. To reduce the number of data points, aggregate the values or apply data filters to the visualization or source element.

### Basic Sankey diagram requirements

To create a Sankey diagram, configure the following properties in the Element properties panel:

* Visualization - chart type displayed in the Dashboard
* Stages - source columns that define the stages and categories
* Value - source column that defines the data path variable

In a Sankey diagram, stages consist of categories presented as individual rectangular nodes that represent data flow start and end points. Data paths illustrate the direction and quantity of data (like energy consumption, expense, page visitors) flowing between categories, with path widths proportional to the value of the data path variable.

### Select the visualization type

Once you add a new visualization to a Dashboard, select the visualization type:

> 📘 In the Visualization property, click the dropdown field and select Sankey from the list.\
> You can also use this dropdown field to convert an existing visualization to a different type. Lifesight retains all property and format configurations shared by the initial and new type. Unshared properties and formatting are not saved or restored if you further convert the visualization.

### Define the stages and categories

Configure source columns to define the stages and categories.

1. In the Stage property, click  Add column and select an option from the menu:

* To generate stage categories based on distinct values in an existing column, search or scroll the Select column list and select the preferred column name.
* To generate stage categories based on a custom formula, select New column and enter the formula in the toolbar.

> 📘 You can also select or replace an existing column by dragging and dropping a column name from the Columns list to the Stage property.

<Image align="center" src="https://files.readme.io/81adfbb509abeb5956113a65ef3840a2a87ee9e72f30a8ecf2d56bbfd63934c7-3d946a5-3.png" />

2. \[optional] Control how the source column data is categorized and displayed in the chart:
   1. Hover over the source column name, then click the caret () to open the column menu.
   2. Hover over any of the following items, then select the preferred option:
      * Truncate date - Categorize date values by the selected interval or unit of measure.
      * Transform - Convert the column to the selected data value type.
      * Format - Display data labels in the selected format.
      > 📘 Availability of column menu items and corresponding options varies depending on the column’s data value type (for example, Truncate date is available for date values only).
3. Repeat the previous steps to configure additional stages (a minimum of two stages are required).
   > 📘 Lifesight charts the stages (as start and end points) in order of precedence, from top to bottom. Drag and drop source column names in the Stage property to reorder them as needed.

<Image align="center" src="https://files.readme.io/acc3fdc1b19ee51dd143228112f81d3638299dc222bbc1cbffe6b8c62e03b0b4-02e110a-5.png" />

### Define the variable

Configure a source column to define the data path variable. Lifesight automatically aggregates column values associated with the initial stage categories to measure the data flow starting points. Within each of these categories, Lifesight aggregates values associated with the subsequent stage categories, then plots these measures as data paths to the end points.

1. In the Value property, click  Add calculation and select an option from the menu:

   * To aggregate values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
   * To calculate values based on a custom formula, select New column and enter a formula in the toolbar.
   * To count the number of rows associated with each stage name, select Row count.

   <Image align="center" src="https://files.readme.io/f4bc50e42998bc37dcfa7b8e8c0b58cbfdc52ceed02ef7713546c1400156aa68-e95a80b-6.png" />

   > 📘 You can also select an existing column by dragging and dropping a column name from the Columns list to the Value property.
2. \[optional] Control how the source column data is calculated and displayed in the chart:
   1. To open the column menu, click the caret () to the right of the source column name.
   2. Hover over any of the following items and select the preferred option:
      * Set aggregate - Calculate values based on the selected aggregation method.
      * Transform - Convert the column to the selected data value type.
      * Format - Display data labels in the selected format.
      > 📘 You can also use the toolbar to change the aggregation method (using the formula) and data label format. If the configurations results in an incomplete chart that exceeds the 25,000 data point limit, apply data filters to reduce the number of data points.
3. \[optional] Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:

   1. To rename a source column, double-click the column name in the Stage or Value property, then enter a new name. Changes are reflected in the default chart title.
   2. To edit the chart title, double-click the title in the visualization, then enter a new title.

   <Image align="center" src="https://files.readme.io/084c40dffdfa26c3717fdd83275d28c4a981e339ace8e91be1cf5cac01dc0fbe-7feb851-8.png" />

> 📘 Lifesight auto-generates the default chart title only. Once the title is customized, it no longer reflects changes to source columns and their names. For information about title customization, see Customize element title.

4. \[optional] In the  Element properties > Marks > Color section, select or customize a color palette to apply to the category nodes and paths.

<Image align="center" src="https://files.readme.io/9e226b7677e09b1e317410c552e35a9a3455877f76533167ac0700c6d2b5ffa6-10cd47b-9.png" />

## Build a funnel chart

Funnel charts are typically used to measure values across sequential stages in a linear process. Create funnel charts to evaluate inputs across each stage and discover potential issues and bottlenecks in a workflow.

This document details basic funnel chart requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

<Image align="center" width="450px" src="https://files.readme.io/aa5e1b46884c8f84fee03d93fb235ed41d3acec69ca39e4c725c5888390681ed-2c15a8a-1.png" />

> 📘 Example use cases:
>
> * Marketing analytics: Monitor an email campaign pipeline to understand where most prospects are being lost, then assess opportunities for greater conversion.
> * Sales analytics: Track the number of prospects in each stage of the sales cycle to identify where most prospects are currently held, then assess investments in specific sales motions.
> * HR analytics: Analyze recruiting process stages by demographics (like age, gender, and application submitted) to measure pipeline dropoff rate for specific candidate groups, then determine if dropoff exceeds expectations and indicates a need for process refinement.

### User requirements

The ability to create funnel charts and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

> 📘 If you're granted Can explore access to the Dashboard, you can create and modify visualization properties and formatting in Explore mode, but you cannot publish your changes.

### Dashboard prerequisite

Before you can build a funnel chart, you must add a new visualization element and select a data source.

At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a funnel chart, Lifesight automatically groups, aggregates, and calculates the underlying data to create source columns for various visualization properties. You can view the underlying data table while configuring the chart to see how the data is applied.

### Basic funnel chart requirements

To display a funnel chart, configure the following properties in the  Element properties panel:

* Chart - chart type displayed in the Dashboard
* Stage - source column that defines the stages
* Value - source column that defines the variable

In a funnel chart, stages reference nominal categories (like campaign pipeline, sales pipeline, recruitment stages) presented as a horizontal bars. A variable measures a value (like number of leads, prospects, candidates) for each stage and determines the width of each bar.

The first stage, shown at the top of the chart, typically represents the initial input of the process and corresponds with the largest stage value (and widest bar). Because value dropoff occurs as data flows through the process, each stage measures a subset of the previous stage value. As a result, the chart progressively narrows and creates a funnel shape.

### Select the chart type

Once you add a new chart to a Dashboard, select the chart type:

* In the Visualization property, click the dropdown field and select Funnel from the list.

<Image align="center" src="https://files.readme.io/8796d78e10c100564cbe094f0916388bdb82554f70e9c59d6ae2fdc5dfd70e6d-d4675b9-2.png" />

### Define the stages

Select a source column to define the stages.

> 📘 When your data source includes a single column with stage names as values, follow the steps below and add this column to the Stage property. Alternatively, if the data source breaks down each stage as a distinct column of data, skip this step and aggregate the individual stage columns in the Value property (see Define the Variable).

1. In the Stage property, click + Add column and select an option from the menu:

* To generate stage names based on distinct values in an existing column, search or scroll the Select column list and select the preferred column name.
* To generate stage names based on a custom formula, select New column and enter a formula in the toolbar.

<Image align="center" src="https://files.readme.io/d97302b537f2664c2e8569bdc5b7e1e3a65df0ae9b8cd1efd19844e825a09d10-3d946a5-3.png" />

### Define the variable

Configure a source column to define the variable. Lifesight automatically aggregates column values associated with the same stage.

1. In the Value property, click + Add calculation and select an option from the menu:

   * To aggregate values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
   * To calculate values based on a custom formula, select New column and enter a formula in the toolbar.
   * To count the number of rows associated with each stage, select Row count.

   <Image align="center" src="https://files.readme.io/dd60377412d5c34b0e927d09f52f021118b7a7a98c98c75f75b0881a9f275a73-e27470a-4.png" />
2. \[optional] Control how the source column data is calculated and displayed in the chart:
   1. Hover over the source column name, then click the caret () to open the column menu.
   2. Hover over any of the following items and select the preferred option:
      * Set aggregate - Calculate values based on the selected aggregation method.
      * Transform - Convert the column to the selected data value type.
      * Format - Display data labels in the selected format.
      > 📘 To plot the source column data without aggregating values, clear the Aggregate values checkbox in the Value property. If this results in an incomplete chart that exceeds the 25,000 data point limit, reaggregate the values or apply data filters to reduce the number of data points.

<Image align="center" src="https://files.readme.io/946a373e6180fd8482d6cbb157c09298afb1526a7f646e0ceb4cb975d228d2f9-096013a-5.png" />

3. \[optional] Repeat the previous steps to configure multiple stage value source columns. Lifesight plots the columns as stacked series on the chart.

<Image align="center" src="https://files.readme.io/1fc9b677acbd19af3420581c46915cc09c0981e821a0091cab08553841478a6b-1957dac-6.png" />

4. \[optional] Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:
   * To rename a source column, double-click the column name in the Stage or Value property, then enter a new name. Changes are reflected in the default chart title.
   * To edit the chart title, double-click the title in the visualization, then enter a new title.

<Image align="center" src="https://files.readme.io/69b8669559aedea641ef1a2bbea1cb4fc77f581fc86a927fae51f73907c24415-53f9d41-7.png" />

### Advanced funnel chart properties and formatting

Lifesight features various properties and format options that give you the flexibility to build detailed funnel charts.

The following sections introduce configurations that can enhance your charts and help you deliver specific insights with meaningful and actionable information.

### Configure mark colors

Configure chart mark colors in the  Element properties > Marks > Color tab to differentiate data.

<Image align="center" src="https://files.readme.io/368330edd0b3677f0b7a4a33a56f833f5262c0bf64c6f36a4f24b81e72e62282-Screenshot_2025-03-10_at_3.38.56_PM.png" />

### Customize data labels

Customize data labels representing conversion rates, stage values, and stage names in the  Element format > Data labels section.

<Image align="left" src="https://files.readme.io/c690130ce9e0c6cb8d155216165871b6162d8804edb9ca47f5e197a971f82f30-Data_labels_SS.png" />

In addition to showing or hiding the different types of data labels, you can customize the font size and color of each.\
You can also select the position of each data label type relative to the chart marks:

<br />

<br />

<br />

<br />

<br />

<Image align="center" src="https://files.readme.io/ae7fb995fc3a64e6288146fa6baef093eda0ef036d1aeb9e7331a40bffa6ac15-Screenshot_2025-03-10_at_3.41.02_PM.png" />

> 📘 The funnel chart’s Color property may determine the availability of specific data labels and positions. For example, stage names can only be displayed inline when the chart features categorical colors that represent stages (see the By category details in Configure mark colors).

When you show conversion rates, you can choose a Percentage style option to determine how conversion rates are calculated:

<Image align="center" src="https://files.readme.io/21e033cc5230885725681fde8e7a0f45ff4cbec1fb88e2091a0c24b918243f60-Screenshot_2025-03-10_at_3.42.59_PM.png" />

## Build a gauge chart

Gauge charts are typically used to display a measurable value against a radial scale. Create gauge charts to evaluate growth, assess performance, or track progress toward a goal.

This document details basic gauge chart requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

<Image align="center" src="https://files.readme.io/64db0959a8c704f9af711219fd30f7d9087a4a6e4b0ed2ea5cd5b8d5daef1b72-fda7059-1.png" />

> 📘 Example use cases:
>
> * IT analytics: Measure implementation completion (as a percentage) to track a project’s progress.
> * Manufacturing analytics: Track machine uptime (as a percentage) to monitor equipment performance.
> * Customer experience (CX) analytics: Measure the net promoter score (NPS) for individual stores or customer service teams to gain insight into customer engagement and loyalty.

### User requirements

The ability to create gauge charts and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

> 📘 If you're granted Can explore access to the Dashboard, you can create and modify visualization properties and formatting in Explore mode, but you cannot publish your changes.

### Dashboard prerequisite

Before you can build a gauge chart, you must add a new visualization element and select a data source.

At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a gauge chart, Lifesight automatically aggregates the underlying data to calculate values for the visualization properties. You can view the underlying data table while configuring the chart to see the unaggregated data.

### Basic gauge chart requirements

To display a gauge chart, configure the following properties in the  Element properties panel:

* Visualization: chart type displayed in the Dashboard
* Value: source column that defines the measurable value
* Minimum: source column that defines the minimum gauge value
* Maximum: source column that defines the maximum gauge value

In a gauge chart, a single value is measured on a radial scale. The minimum and maximum values determine the range of the gauge and provide reference points for assessing the measurable value.

### Select the visualization type

After you add a new visualization to a Dashboard, select the visualization type:

* In the Visualization property, click the dropdown field and select Gauge from the list.

<Image align="center" src="https://files.readme.io/4c81162ac477800fee688e88b331d7418d8de23d20620a1b64d26c2f67f3dfbe-f8b6c27-2.png" />

> 📘 You can also use this dropdown field to convert an existing visualization to a different type. Lifesight retains all property and format configurations shared by the initial and new type. Unshared properties and formatting are not saved or restored if you further convert the visualization.

### Define the measurable value

Configure a source column to define the measurable value.

1. In the Value property, click + Add calculation and select an option from the menu:
   * To aggregate the values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
   * To apply a custom formula or constant value, select New column and enter the formula or value in the toolbar.
   * To count the number of rows in the data source, select Row count.
   > 📘 You can also select or replace an existing column by dragging and dropping a column name from the Columns list to the Value property.
2. \[optional] Control how the data is calculated and displayed in the chart:
   1. Hover over the source column name, then click the caret () to open the column menu.
   2. Hover over any of the following items, then select the preferred option:

      * Set aggregate - Calculate the value based on the selected aggregation method.
      * Transform - Convert the column to the selected data value type.
      * Format - Display the data label in the selected format.

      <Image align="center" src="https://files.readme.io/8c18579f8ea7bdd1da6962869950fd51c8c1b3c77c2480819a1373671b314dc2-614dfc9-4.png" />

> 📘 You can also use the toolbar to change the aggregation method (using the formula) and data label format.

### Define the gauge range

Configure a source column to define the minimum and maximum gauge values.

1. In the Minimum property, click + Add calculation and select an option from the menu:
   * To aggregate the values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
   * To apply a custom formula or constant value, select New column and enter the formula or value in the toolbar.
   * To count the number of rows in the data source, select Row count.
   > 📘 You can also select or replace an existing column by dragging and dropping a column name from the Columns list to the Minimum property.

<Image align="center" src="https://files.readme.io/110d1cc9eeebbfd94db392e83b4e5f576ad05e98f801eb5cdb5a7976267caf02-e1a3940-5.png" />

2. In the Maximum property, click  Add calculation and select an option from the menu:
   * To aggregate the values of an existing column, search or scroll the Aggregate column list and select the preferred column name.
     * To apply a custom formula or constant value, select New column and enter the formula or value in the toolbar.
     * To count the number of rows in the data source, select Row count.
     > 📘 You can also select or replace an existing column by dragging and dropping a column name from the Columns list to the Maximum property.

<Image align="center" src="https://files.readme.io/ebb7398234aff03533f1e4ee6f6bd2c54fd8e431fa9918a4acd19cc1ebdaf47f-8d82137-6.png" />

3. \[optional] Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:
   * To rename a source column, double-click its name in the Value, Minimum, or Maximum property, then enter a new name. Changes to the Value property are reflected in the default chart title.
   * To edit the chart title, double-click the title in the visualization, then enter a new title.
   > 📘 Lifesight auto-generates the default chart title only. Once the title is customized, it no longer reflects changes to the Value property.

<Image align="center" src="https://files.readme.io/b36274dfd6386e10e2e6de953ca765b974761f70add3f8bc0c7a5c385f6890d5-3db1dc7-gauge_define-gauge-range_step-3.png" />

### Advanced gauge chart properties and formatting

Lifesight features various properties and format options that give you the flexibility to build detailed gauge charts.

The following sections introduce configurations that can enhance your charts and help you deliver specific insights with meaningful and actionable information.

### Configure target value

Configure a target value in the  Element properties > Target property to mark a goal or benchmark on the gauge. The Target property can be configured in the same way as the Value, Minimum, and Maximum properties.

<Image align="center" src="https://files.readme.io/c040435b84d5d4826597f82dd5295135b725344308af9e46c18098d5a8727587-8c7263d-8.png" />

### Configure chart colors

Configure chart colors in the  Element properties > Color property.

<Image align="center" src="https://files.readme.io/4f200bc08c4a0f0999ff4b73c8fb4ad5ae5f8eac665a3de5c929d2785909e42c-Screenshot_2025-03-10_at_4.21.51_PM.png" />

### Add conditional formatting

When you select Single color in the  Element properties > Color property, you can configure formatting rules (+ Add rule) that determine the gauge fill or gauge scale color according to value- or percentage-based conditions.

By default, conditional formatting applies to the gauge fill color (representing the measurable value), but you can apply rules to the gauge scale by selecting the Show color on gauge checkbox. This option hides the gauge fill and conditionally formats segments of the gauge based on values or percentages along the radial scale.

Example:

<Image align="center" width="600px" src="https://files.readme.io/0e8258a2402bfdc0d4d7f071acb06b369251fa74db7d492e894f52fda93a2bce-Screenshot_2025-03-10_at_4.23.48_PM.png" />

> 📘 When the conditions of multiple rules are met, Lifesight applies the formatting rules in order of precedence, from top to bottom. Drag and drop rule blocks to reorder them as needed.

When you create a value-based rule, Lifesight evaluates the measure or gauge scale value. If the value meets the conditions defined in the Formatting rule fields, the color selected in the Style field applies to the gauge fill or gauge scale.

Example:

<Image align="center" src="https://files.readme.io/dab824991eb865a6841e65703a2bfa42875f8f42b4c90600d614c1c7c6564b8e-Screenshot_2025-03-10_at_4.24.56_PM.png" />

When you create a percentage-based rule, Lifesight evaluates the measure or gauge scale value relative (as a percentage) to the maximum or target value, depending on the rule configuration. If the percentage meets the conditions defined in the Formatting rules field, the color selected in the Style field applies to the gauge fill or gauge scale.

<Image align="center" src="https://files.readme.io/e0612f9de9fa63e9dbdb98db0bad4147ad2149b809cb68886a096aef682ddf04-28dd9bf-12.png" />

Example:

<Image align="center" src="https://files.readme.io/42a69d065afaee78adffaa1dd3c1dfab380f652bf86d5fb3dd16992b8afc1ec1-Screenshot_2025-03-10_at_4.26.26_PM.png" />

### Customize gauge marks

Customize gauge marks (gauge, needle, and target) in the  Element format > Gauge marks section.

<Image align="left" src="https://files.readme.io/0e5c7ad12bcf27e2507b25ddea29a7b32e0f7ae63f6451a152f9ac31aa7eacd9-6262e83-14.png" />

<Image align="center" src="https://files.readme.io/6da000c4362efd09379a3fcc4b619c37a4ca90e26afcd1470627370b0d8fcb88-Screenshot_2025-03-10_at_4.34.07_PM.png" />

<Image align="center" src="https://files.readme.io/56c2e28280add6c39b09f6b4b9f193d3cca58596425b67ee06a7b6ed7026fd98-Screenshot_2025-03-10_at_4.34.24_PM.png" />

## Build a geography map

Geography maps (Map - Geography visualization type) support datasets with geography data (WKT format) or variant data (GeoJSON format) and are typically used to illustrate geospatial objects on a map. Create a connection map to display spatial networks, correlations, and relationships, or build a choropleth map to identify variability and patterns across distinct geographic areas.

<Image align="left" src="https://files.readme.io/60e104810e143395526b4181d8ad28ce6b321e932cc23678cd4304ab2c281526-geography-map.png" />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

<br />

> 📘 Example use cases:
>
> * Land use analytics: Represent land parcels by zoning code to identify land use patterns and conflicts with proximal areas
> * Marketing analytics: Quantify customers across specific regions to analyze customer distribution and understand market reach.
> * Environmental analytics: Map oil and gas pipelines to assess proximity to residential areas and natural resources.

### User requirements

The ability to create geography maps and other visualizations requires the following:

* You must be assigned an account type with the Create, edit, and publish Dashboards and/or Explore Dashboards permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

If you’re granted Can explore access to the Dashboard, you can create and modify visualization properties and formatting in Explore mode, but you cannot publish your changes.

### Data prerequisites

A geography map requires one of the following data types:

* Geography data (WKT)
* Variant data (GeoJSON)

If your dataset isn’t compatible, you may be able to use functions (such as type or geography functions) to convert data to a supported type. Alternatively, when building a choropleth map, you can also use the Map - Region visualization.

### Geography map variations

<Image align="center" src="https://files.readme.io/49f919cc53126e319d74bc1a880066030ba857e4fef41d204964a03b0be9c4d0-Screenshot_2025-03-10_at_4.46.17_PM.png" />

> 📘 The Map - Geography visualization doesn't support point (link) maps.
>
> However, you can build point maps using the Map - Point visualization if your dataset contains geospatial data that represents points.\
> If points are represented by the geography data type, use the Latitude and Longitude functions to extract the coordinates from the WKT format. If points are represented by the variant data type, select the Extract columns option in the column menu to extract the coordinates from the GeoJSON format. You can then plot the extracted data in the Map - Point visualization.

### Basic geography map configurations

Geography maps require the following element properties:

* Visualization: chart type used to illustrate the data
* Geography: source column that defines the geospatial objects

> 📘 At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build a geography map, Lifesight automatically calculates and structures the data to map the element properties to source columns in the underlying data table. For information about how to view the underlying data while you configure the chart, see Maximize or Minimize a Data Element.

### Add a geography map

Create a new visualization element and designate it as a geography map.

* Open a Dashboard in Explore or Edit mode and add a new visualization element.
* In the new element’s Visualization property, click the dropdown field and select Map - Geography from the list.

<Image align="center" src="https://files.readme.io/ff41d39ec00840a029cc7186da981f1dcc55c8d58105d9615902c30763cd4cc1-geography_select-visualization-type.png" />

### Define the geospatial objects

Configure a source column that defines the geospatial objects (lines or polygons) representing landmarks, routes, regions, or other features. The column must contain geography data in WKT format or variant data in GeoJSON format.

1. In the Geography property, click  Add column and select an option from the menu:

   * To map objects from an existing column, search or scroll the Select geography/variant column list and select the column name.
   * To create a new column using a custom formula, select Add new column and enter the formula or value in the toolbar.

   <Image align="center" src="https://files.readme.io/3ac6681bf48b19e344c0bb87a8e657322c577b117237403425c79bba88dc9d7d-geography_select-geography-source-column.png" />

When the Geography property is configured, the map illustrates the geospatial objects represented by the source column data.

<Image align="center" src="https://files.readme.io/2dfee7d0a10610c34041b8ed9c9d06df1c1ab0ac99d2bc7e8139588f2541da48-geography_illustrate-geospatial-objects.png" />

### Advanced geography map properties and formatting

#### Configure mark colors

Configure the line or polygon mark colors in the  Element properties > Marks > Color tab to visualize patterns, highlight variations, improve readability, and more.

<Image align="center" src="https://files.readme.io/92098ecd97a73efe27d2e23eacf8246352d7ae8e7e36bbef4f24e20c53868fec-Screenshot_2025-03-10_at_4.50.54_PM.png" />

### Customize tooltip fields

Configure source columns in the  Element properties > Marks > Tooltip property to add fields to the map tooltips.\
If a source column is configured in the Marks > Color property, its values are automatically displayed in the tooltips. For information about changing tooltip defaults and adding fields, see Customize chart mark tooltips fields.

<Image align="center" src="https://files.readme.io/a1237d23891f51c3798f1ced25a1abadf78626ef352205b486434281358062fd-geography_marks_tooltip_add.png" />

### Change map style

Change the base style of your map in the Element format > Map style section.

<Image align="center" src="https://files.readme.io/600d213c9c0b31524d19a75c51ceefbb09c8912ea064fb639a6db3f9afe5386c-geography_format_map-style.png" />

<Image align="center" src="https://files.readme.io/8ec05a6cbedf116b9e32dd9b17a4f84610731e630eebd20120da4a4e98378c20-Screenshot_2025-03-10_at_5.20.01_PM.png" />

<Image align="center" src="https://files.readme.io/7b3f47e37249bf0af7c8d09617db03f701814d5e2cc0cb7101a0dac4e03b07f3-Screenshot_2025-03-10_at_5.20.13_PM.png" />

<Image align="center" src="https://files.readme.io/b0e650834423f5807022c934b50a6bb23b3980cac5a521c44e8cfdafda916b9b-Screenshot_2025-03-10_at_5.20.25_PM.png" />

## Build a waterfall chart

Waterfall charts are typically used to show changes in one or two categories of data over a period.

This document details basic waterfall chart requirements and introduces key properties and format options to help you enhance your Dashboard visualizations.

<Image align="center" src="https://files.readme.io/8a9c8c0c207d1742c3e56b9215763ff7bc5a639e4185b921edbf00d8812daa43-5633508-waterfall-thumbnail_1.png" />

> 📘 Example use cases:
>
> * Accounting analytics: Measure the positive and negative contributions to an overall budget.
> * Financial analytics: Track revenue and spend for a project, department, or an entire organization.
> * Retail analytics: Track positive and negative foot traffic over time for a store or region.
> * HR analytics: Measure employee retention rates as part of total employee headcount tracking.

### User requirements

The ability to create waterfall charts and other visualizations requires the following:

* You must be assigned an account type with the Edit Dashboard and/or Explore Dashboard permission enabled.
* You must be the Dashboard owner or be granted Can explore or Can edit Dashboard permission.

### Basic waterfall chart requirements

To plot a waterfall chart, configure the following properties in the  Element properties tab:

* Visualization: Chart type displayed in the Dashboard
* X-axis: Source column that defines the x-axis (horizontal axis) categories or variable
* Y-axis: source column that defines the y-axis (vertical axis) categories or variable

In a waterfall chart, one axis typically represents ordinal or nominal categories (like stages, regions, departments) presented as vertical or horizontal bars. The other axis represents a variable that measures a value (like sales, leads, expenses) for each category and determines the height of the corresponding bar. The type of data affiliated with each axis depends on the chart orientation, which you can modify at any time.

> 📘 At the core of every visualization is an underlying data table (derived from the data source) that supplies the information visualized by the chart. As you build your chart, Lifesight automatically calculates and structures the data to map the element properties to source columns in the underlying data table.

### Add a waterfall chart

Create a new visualization element and designate it as a waterfall chart.

1. Open a Dashboard in Explore or Edit mode and add a new visualization element.
2. In the Visualization property, click the dropdown field and select Waterfall from the list.

📘\
You can also use this dropdown field to convert an existing visualization to a different type. Lifesight retains all property and format configurations shared by the initial and new type. Properties and formatting not shared by the new type are not retained.
Define the categories
Define the categories for the chart by configuring a source column to use. Because waterfall charts are best for showing change over time, select a date column:
In the X-axis property, click  Add column and select an option from the menu:
To generate categories based on distinct values in an existing column, search or scroll the Select column list and select the column name.
To generate categories based on a custom formula, select New column and enter the formula in the toolbar.
Select or replace an existing column by dragging and dropping a column name from the Columns list to the applicable axis property.
\[optional] Adjust how the source column data is categorized and displayed in the chart:
Hover over the source column name, then click the caret () to open the column menu.
Hover over any of the following items, then select option you want to use:
Truncate date - Categorize date values by the selected interval or unit of measure.
Transform - Convert the column to the selected data value type.
Format - Display axis and data labels in the selected format.
📘
Availability of column menu items and corresponding options varies depending on the data type of the column. For example, Truncate date is only available for date values.
Define the variable
Define the chart variable, or what has changed over time, by configuring a source column. When you add a source column, Lifesight automatically aggregates values associated with the same chart category.
In the Y-axis property, click  Add calculation and select an option from the menu:
To aggregate values of an existing column, search or scroll the Aggregate column list and select the column name.
To calculate values based on a custom formula, select New column and enter the formula in the toolbar.
To use a count the number of rows associated with each category, select Row count.
📘
This visualization supports up to 25,000 data points. If the configurations result in a data set that exceeds this limit, the visualization displays the first 25,000 data points, and a warning message indicates that the chart is incomplete. To reduce the number of data points, aggregate the values or apply data filters to the visualization or source element.

💡\
You can also select an existing column by dragging and dropping a column name from the Columns list to the applicable axis property.
\[optional] Adjust how the source column data is calculated and displayed in the chart:
Hover over the source column name, then click the caret () to open the column menu.
Hover over any of the following items, then select the option you want to use:
Set aggregate - Calculate values based on the selected aggregation method.
Transform - Convert the column to the selected data value type.
Format - Display axis and data labels in the selected format.
📘
To plot the source column data without aggregating values, clear the Aggregate values checkbox in the Y-axis property. If this results in an incomplete chart that exceeds the 25,000 data point limit, aggregate the values again or apply data filters to reduce the number of data points.
💡
You can also use the toolbar to change the aggregation method (using the formula) and data label format.
\[optional] Repeat the previous steps to add additional y-axis source columns and create a stacked waterfall chart.
By default, a waterfall chart shows the sum of values over time. If you only have one y-axis source column, you can change the display formatting to show the difference in values across each period. See Customize waterfall shape.
Customize your waterfall chart
Lifesight auto-generates source column names and chart titles to reflect the visualized data, but you can customize these fields as needed:
To rename a source column, double-click the column name in the X-axis or Y-axis property, then enter a new name. Changes are reflected in the default chart title.
To edit the chart title, double-click the title in the visualization, then enter a new title.
📘
Lifesight auto-generates a default chart title. After you customize the title, the chart title no longer reflects changes to source columns and their names.
Advanced waterfall chart properties and formatting
Lifesight features various properties and format options that give you the flexibility to build advanced waterfall charts, including stacked waterfall charts.
The following sections introduce configurations that can enhance your charts and help you deliver specific insights with meaningful and actionable information.
Change stacking
When you add multiple source columns, the values are stacked by default. You can change the chart formatting to remove the stacking.

Stacking

No stacking\
Plot multiple data series as separate waterfall charts with subtotals for each series.

Stacked\
Plot multiple data series as cumulative waterfall segments. Compare subcategory contributions to each category’s total sum value in the resulting stacked waterfall chart.

Configure mark colors\
Configure waterfall mark colors in the  Element properties > Marks > Color tab to differentiate data and highlight specific values.

By series\
Select a color for the increase, decrease, and total values for the waterfall chart. For information about adding formatting rules, see Add conditional formatting in this document.

Add conditional formatting\
In the  Element properties > Marks > Color tab, you can configure formatting rules (+ Add rule) that determine waterfall mark colors according to value-based conditions, in addition to the increase and decrease colors used for the waterfall chart.

Example:

💡\
When the conditions of multiple rules are met, Lifesight applies the formatting rules in order of precedence, from top to bottom. Drag and drop rule blocks to reorder them as needed.
Customize tooltip fields and values
Customize chart mark tooltip fields in the  Element properties > Marks > Tooltip tab to display the most relevant metrics and data attributes. For more information, see Customize chart mark tooltip fields.
For example, you can customize the default tooltip by removing the X-axis chart value from the tooltip and adding a new aggregate column, showing a distinct count of SKU numbers, in the Tooltip tab.
Default
Custom column in tooltip

Customize waterfall shape\
You can customize the shape of the waterfall. In  Element format, select Waterfall shape and configure the available options.
Set the calculation to display
You can only choose the calculation to display for waterfall charts that display one source column (are not stacked).

Sum displays the sum of the values over time.

Difference displays the difference in values between each period.

Configure the start value\
Choose from several options for the start value of your waterfall chart:

First value in data uses the first value in the data as the starting point for the chart. Default value.

None does not display a start value and the first value in the data displays as part of the waterfall.

Custom uses a constant value or an aggregated column as the starting value. If you select a Custom start value, you can customize the start value label.

Configure the end value

Select the Show end value checkbox to display an end value. The end value is shown by default.

For End value label, enter a label to describe the end value on the waterfall chart.

Show connector lines\
Select the Show connector line checkbox to show a line connecting the values on the waterfall chart. You can then select a Connector line color.
Default
With connector lines

All waterfall chart format options\
Background
Title
X-axis
Y-axis
Legend
Data labels
Reference marks