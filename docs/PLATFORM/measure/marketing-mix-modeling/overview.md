---
title: MMM Overview tab
excerpt: >-
  Analyze your MMM metrics summary, platform spends vs KPI graph, MMM model
  input data, and correlation matrix from your MMM model.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In the Overview tab, you can view your overall marketing performance reports and conduct a preliminary analysis based on historical data you have uploaded or integrated. Understanding these reports is crucial for gaining actionable insights into your marketing performance.

<Embed url="https://www.youtube.com/watch?v=3bgL3m-io78" href="https://www.youtube.com/watch?v=3bgL3m-io78" typeOfEmbed="youtube" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fwww.youtube.com%252Fembed%252F3bgL3m-io78%253Ffeature%253Doembed%26display_name%3DYouTube%26url%3Dhttps%253A%252F%252Fwww.youtube.com%252Fwatch%253Fv%253D3bgL3m-io78%26image%3Dhttps%253A%252F%252Fi.ytimg.com%252Fvi%252F3bgL3m-io78%252Fhqdefault.jpg%26key%3D7788cb384c9f4d5dbbdbeffd9fe4b92f%26type%3Dtext%252Fhtml%26schema%3Dyoutube%22%20width%3D%22854%22%20height%3D%22480%22%20scrolling%3D%22no%22%20title%3D%22YouTube%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

Here's a list of the different fields in the MMM Overview tab:

## Date range

Select the date range from your MMM input data to view insights for the selected period.

<Image align="center" width="600px" src="https://files.readme.io/d4b095a1ea3d7c238fde6e61260f5093b51057ed3be257b88295aad53dd72c42-Screenshot_2025-07-22_at_5.08.23_PM.png" />

<br />

## Version

By default, Lifesight selects the most suitable model version and displays it in the Versions tab based on various criteria.

You can select any model from the list of top 5 models based on paid contribution, non- paid contribution, NRMSE, Estimation error. In general, Non-paid contribution would include: Baseline, Contextual, Organic, Seasonality, Trend.

### How to change model version?

Click the `Settings` icon to view the top 5 models. This allows stakeholders to review and select the best model based on their business needs. Learn more about how top models are shortlisted here.

<Image align="center" alt="Model versions" border={false} caption="Model versions" src="https://files.readme.io/998a5d9d64afcae1cb0e326296941e12ddff56248b3726de368e4604674aaa6c-Screenshot_2025-07-22_at_5.06.26_PM.png" />

<br />

> ❗️ If you change the default selected model, the Optimize for KPI won't be accessible in the Planner.
>
> You will have to contact the marketing science team to enable optimize for KPI in the Planner.

These metrics ensure robust model fit and accuracy, helping stakeholders choose the most appropriate model for strategic use.

<br />

## Metrics summary

View a high-level view of key metrics such as total revenue, total spend, blended ROAS and other important metrics.

![](https://files.readme.io/430646e812e305da80b85bd278b2c2e2cb4dda80ac748a9de2f0719c0f230836-image.png)

<br />

## Platform spend vs. KPI

The graph shows your marketing spending from all platforms in columns and overlays the KPI as a line. Select the drop-down filter in the right to filter spends vs revenue by each channel to view the trend over time.

![](https://files.readme.io/6f5c82949af4fe1431bf81c14f22a873ad44819b54dae4b0e08a1c0fc0f64d1f-image.png)

<br />

## Model Input

The chart shows all the Marketing Mix Model (MMM) input data, including data from integrations, in a simple, date-aligned table. You can use this chart to check data trends and see how the integration inputs perform over different periods.

![](https://files.readme.io/6e1b13e146af5d79304ca393cb4e2af674fd32d285c6987b2a4415cd350663d3-image.png)

<br />

## Correlation Matrix

A correlation matrix is a square matrix chart showing the correlation coefficients between two variables. The matrix shows how all the possible pairs of variables in a table are related to each other. This chart helps in summarizing a large data set and finding and showing correlation-based patterns in the data.

**Reading the chart:**

Each of your input variables is listed in both the rows and the columns and the correlation coefficient between each pair of variables is written in each cell. The correlation coefficient ranges from -1 to +1, where -1 means a perfect negative correlation, +1 means a perfect positive correlation, and 0 means there is no correlation between the variables.

![](https://files.readme.io/a1fd7b28651b90f1e35ec403c9fc83e67e0b4451ae14e42b9cd9c75eb677ca2f-image.png)

<br />

By clicking on a specific cell, you can visualize the detailed correlation scatter plot between two variables.

<br />

**How to interpret a Scatter Diagram**?

![](https://files.readme.io/290683d10be36e564e88ea497718600b12a2ecf06c8dd073cfef6f9db6a93f17-image.png)

While interpreting a scatter diagram, the given below points should be taken into consideration:

* **Dense or Scattered Points:** If the plotted points are close to each other, then you can expect a high degree of correlation between the two variables. However, if the plotted points are widely scattered, then you can expect a poor correlation between the variables.
* **Trend or No Trend:** If the points plotted on the scatter diagram show any trend either upward or downward, then it can be said that the variables are correlated. However, if the plotted points do not show any trend, then it can be said that the variables are uncorrelated.
* **Upward or Downward Trend:** If the plotted points show an upward trend rising from the lower left-hand corner of the graph and going upward to the upper right-hand corner, then the correlation is positive. It means that the two variables move in the same direction. However, if the plotted points show a downward trend from the upper left-hand corner of the graph to the lower right-hand corner, then the correlation is negative. It means that the two variables move in the opposite direction.
* **Perfect Correlation:** If the points plotted on the scatter diagram lie on a straight line and have a positive slope, then it can be said that the correlation is perfect and positive. However, if the points plotted lie on a straight line and have a negative slope, then it can be said that the correlation is perfect and negative.

If most of the points are dense and show a trend, a few outliers may lead to a lower correlation number, but they are well correlated.