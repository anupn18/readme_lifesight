---
title: Model creation
excerpt: Create your first MMM model in minutes and get incremental insights
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
  pages:
    - type: basic
      slug: overview
      title: MMM Overview
---
Marketing Mix Modeling (MMM) can account for a variety of variables that influence marketing performance. These include media variables like TV, radio, digital ads, and social media spend, which capture the effect of different channels. MMM also considers external factors such as seasonality, economic conditions, and competitive activity. Additionally, it accounts for internal business factors like pricing, promotions, and product launches, as well as non-media variables like distribution and brand equity. This comprehensive analysis helps determine the contribution of each factor to sales or other KPIs.

## View interactive demo

<Embed typeOfEmbed="iframe" url="https://lifesight.storylane.io/share/2ckzf7dpatbk" html="false" iframe="true" href="https://lifesight.storylane.io/share/2ckzf7dpatbk" height="600px" width="800px" />

<br />

# Steps to create a MMM model

1. Navigate to the MMM module (Measure > Models). Select `Create Model`.
2. Name your model in the top-left section.
3. Upload data using CSV file ([template](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1368124972#gid=1368124972)) or utilize**Integrated Data** and click `Next`
4. In the `Features` tab:
   1. Map your `Outcome KPI` to `Data type`.
   2. Map your `Paid marketing spend` to a `Platform`
   3. Map your `Paid marketing clicks` to a `Platform`.
   4. Map your `Paid marketing impressions` to `Platform`.
   5. Map the `Impact` and `Factorial/Categorical` parameter for your `Organic` marketing variables.
   6. Map the `Impact` and `Factorial/Categorical` parameter for your `Contextual` marketing variables.
   7. Map the `Impact` and `Factorial/Categorical` parameter for your `Halo` marketing variables.
5. In the `Configure the model` tab.
   1. Select `Aggregation` type - Daily, Weekly, Monthly.
   2. Select `Date` range.
   3. Enable/Disable Pre-configured contextual variables like `Seasonality, Weekdays, Holidays, Trends, Intercept` and mention the `Impact` (Positive, Negative, Neutral) based on the relation they have with your outcome KPI. (based on domain/industry knowledge)
   4. Mention the Country, Currency, Refresh Frequency, and Training Size.
   5. Modify model hyper-parameters from Advanced settings (optional)
   6. Finally, selected `Create Model` to create a MMM model.

> 📘 Advanced settings
>
> Data & Marketing Scientists can modify model hyper parameters such as **Adstock and Saturation and Calibrate** MMM models from the Advanced setting dropdown in the bottom of the `Configuration` tab.

<br />

Watch the <Anchor label="interactive demo" target="_blank" href="https://lifesight.storylane.io/share/2ckzf7dpatbk">interactive demo</Anchor> for a step by step guidance on creating a Model based on your requirements.

***

<br />

# Guidelines for Model building

### Uploading data using CSV file

> 🚧 Before uploading CSV file some conditions must be checked.
>
> 1. Date should be in format [yyyy-mm-dd](http://yy-mm-dd.Date) Date can we daily, weekly or monthly. For weekly data it should start from sunday or monday.
>
> 2. No date should be missing.
>
> 3. All the independent variables like spends, impressions, clicks, organic variables and contextual variables should be numeric. There should be no missing values.
>
> 4. Replace null values with. 0, unless null values are treated using a different method.
>
> 5. None of the independent variables count should be 0. If the sum of the column is zero please drop that column before creation of model, to avoid encountering an error.
>
> 6. Column headers should only contain alphanumeric characters and underscores.
>
> 7. The heading should start with an alphabet only.
>
> Note: Once the CSV file is ready you can just open in notepad or sublime to check there should be no string values. Sometimes string value gets created in the last rows of CSV file.

<br />

### Uploading data using Integrated method

For the Integrated method, connect ad channels so that data can be pulled directly from the platform. The data connection pulls in ad Insights such as paid media variables data and KPI (Dependent variables) from Events table. To upload offline data, simply collect your data spends and KPIs in a Google sheet in CSV format and integrate the sheet.

* Select the data type you are integrating. In this you need to select data type i.e whether mmm, cogs or custom\_costs. For marketing mix modelling , mmm needs to be selected.
* Select how often the data needs to be refreshed.
* Next, authenticate your google account to grant access to Lifesight to read data from Google workspace. Once the authentication is done Google Sheets is integrated and you can see Google Sheets MMM status change to "Active"

<Image align="center" width="500px" src="https://files.readme.io/543ca39edcb99ddd96d07a96d037fe9da402bcd1d3fe6077f2895948f494ad20-image.png" />

<br />

Before using the Integration method, make sure you setup the [Google Sheets MMM data integration](https://docs.lifesight.io/docs/google-sheets-mmm-data-integration) from the Integrations section in the Lifesight dashboard. Once your integration is active, choose "Using Integrated data" in the MMM upload data section to automatically pull all your input data from the integrated MMM data sheet.

<Image align="center" src="https://files.readme.io/4763a9b700e3f2e1db2a3a0494db28cb23a5a38a3312203440ca47a9bce5c528-integrations.jpg" />

<br />

### Selecting Features (Schema Mapping)

If you have uploaded a custom MMM dataset, map the schema by associating your input data with Lifesight's data types. If you are using integrated data, this step is unnecessary.

<Image align="center" src="https://files.readme.io/1ab05cf53e505ad1d25febbee3d4cc1cd911bf726857ab732855c96c41026ce1-feature.jpg" />

* Select data (name of the data column in your uploaded sheet), specify the aggregation type whether data in csv file is of daily, weekly or monthly type. Also select the start date.
* Select the KPI (dependent variable) from the sheet. KPI can be revenue, orders, new customers, sales. Also map the datatype for your KPI.
* Select the spends, impressions and clicks for various variables and map with the platform name. These (Spends, impressions, and clicks)  can be available at channel or tactic level. It all depends on which level you are building the model.
* Input organic and contextual variables, specify the data type of the variable. We can also predefine the impact of these variables on KPI as positive or negative (if you known the impact on KPI) else mark it as neutral.

> 📘 Examples for selecting Impact:
>
> * Own brand promotions would have a positive impact for any ecommerce or retail brand while competitor promotions can have a negative impact.
> * Holidays would have a positive impact for a consumer electronics business during holidays periods - Christmas, Thanksgiving, and New Years.

<br />

## Configuring a model

In the configuration page select the country, currency, training size, and hyperparameters for variables and calibration.

<Image align="center" src="https://files.readme.io/22d9348a42a491f74b8650ec992f9385a212817c2bb370c7ae965ca42f6c3c6c-config.jpg" />

1. Select the aggregation type as Daily, Weekly, or Monthly based on your input data and choose the start date.
2. Toggle Seasonality, Holidays, and Trends as ON/OFF.
3. Choose your Country, Currency, Refresh frequency, and Training size.

> 📘 Note
>
> #### Pre-configured Contextual Variables
>
> Mentioning the impact of these variables helps guide the model on the impact of Seasonality, Holidays, Trends, Intercept on outcome KPIs. The Impact could either be Positive, Negative, or Neutral.
>
> #### Country, Currency, and Refresh frequency
>
> * Country - Selecting a country helps the model account for holidays and other country specific data that could improve model accuracy
> * Currency - Selecting a currency helps show all spends and revenue in the currency of your choice.
> * Refresh frequency - Select the refresh frequency to keep your model updated in real-time.
>
> #### Training Size
>
> Lower bound and Upper bound instruct the model on what percentage of MMM input data to use for training the model. The excluded data from the MMM training process can be used for backtesting and validation to check the model accuracy using real-world data.
>
> *Example: Lower bound = 0.85; Upper bound = 0.9 - This means the model uses 85-90% of input data for training purposes.*

<br />

### For advanced users (data/marketing science teams)

Modify adstock, and saturation for every channel. Also, calibrate your model through experiment results.

<Image align="center" src="https://files.readme.io/cfdd1615de9311232f64a5cc8d8c3db4e5995454ea4725f2afe88ab8a88031d0-advanced.jpg" />

1. Adjust the adstock transformation for every channel. Choose between 2 types of methods.
   1. Geometric OR
   2. Flexible (Weibull PDF)

*Note: We recommend selecting "Flexible" as Geometric is a subset of Weibull PDF type for transformation. Lifesight automatically recommends a range for hyperparameters for both linear and flexible adstock transformation.*

2. Adjust the Saturation level for every channel
3. Enter Calibration metrics at the bottom of the Configuration tab, only if you have run successful Experiments, else leave it empty. This helps calibrate your MMM model with new insights by adjusting the contribution and incrementality factor for all your channels based on the calibration insights.

![](https://files.readme.io/cab993174f039fc6179208e08b5bb706604f65743894f5c6e6f0cedeba35d09e-image.png)

<br />

> 📘 Note
>
> In first run of the model we can use the suggested range of hyperparameters and subsequently in next trial we can change the range if needed (if you have the knowledge that for particular channel the range should be something else but it should be under certain range as defined).
>
> For Calibration select from the platform for what particular channel you want to calibrate. Specify the date(start and end date), spend done on that time period, incremental and confidence level.

<br />

## Step 4: Calibrate your model

The Calibration tab allows users to enhance their models by incorporating historical observations or experimental results into the model. This calibration process improves the accuracy and quality of insights generated by the model. Enter your channel, spend, incremental lift, and a confidence score to train your model.

> 🚧 If you want run a new experiment and calibrate your model, you can select the Re-calibrate button in the MMM model tab to add your new experiment insights.

<Image align="center" src="https://files.readme.io/fe47c4c72ad1a26897d746fbf5062807319af65d020314eba3c55520dbac9942-calibrtae.jpg" />

## Step 5: Finally, select "Create Model"

Once you select `Create model` your Model status changes to "Under training". It typically takes about 1 hour to create a model and get insights.

Once the model has run successfully the status changes to "Success".

<Image align="center" src="https://files.readme.io/80dd6ce3f0da5c4cc8ace65d6b88738cb0b2484eff32e469616a47f885e60889-training.jpg" />

<br />

Once you've successfully created a model, it's time to uncover the insights your model generated in the MMM Overview tab.