---
title: Google sheets
excerpt: Automate your MMM data & COGS data refresh from your google sheets
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Integrating Google Sheets will enable your data to help onboard MMM, Spends and Product COGS Data within Lifesight. 

**Navigation:**

1. Go to the Connect module > Integrations.
2. To integrate your MMM data search for "Google Sheets MMM" in the search box. To integrate your COGS and product data search for "Google Sheets".
3. Select your desired integration to open up the integration page.

***

## Integrate Google Sheets:

![](https://files.readme.io/0942725fc398289b55ac3fb391ac91004d9746024d5e49fd702039a21009e8e2-image.png)

<br />

### Step 1: Select the Data Type

Select the purpose for which the data will be utilized: MMM, Custom Spends, or COGS, and specify the desired data granularity level present in the sheet: Daily, Weekly, or Monthly. Column headers can only contain either alphanumeric characters or an underscore, and must start with an alphabet

* Data type - Select if your data is COGS or custom costs.
* Data granularity - Choose from daily, weekly, and monthly granularity.

### Step 2: Select your data refresh frequency

Select your refresh frequency to either be daily, weekly or monthly and specify the time at which the refresh should take place. Date format should be YYYY-MM-DD

### Step 3: Authenticate your Google Account

Click the `Authenticate` button to authorize your Google account.

***

## Integrate Google Sheets MMM

![](https://files.readme.io/53cdc8ce1f9fbf7e4a4e677e4389f355e20acb16ddae4fa18b81fef7d277398d-image.png)

<br />

### Step 1: Upload the MMM google sheet

Ensure your data is as per the [MMM data schema template](https://docs.google.com/spreadsheets/d/17UgnDqvQyHz_3XFFa-DSHdk80fudK1mt9p7Stj-xhdI/edit?gid=1368124972#gid=1368124972) in CSV format.

### Step 2: Select your data refresh frequency

Select your refresh frequency to either be daily, weekly or monthly, and specify the time at which the refresh should take place. Date format should be YYYY-MM-DD

> 👍 The MMM model will refresh automatically based on the set frequency.

* Select `Settings`button from the top-right to update the refresh frequency or data type.
* Click the `Refresh` button to refresh your data manually.
