---
title: Activating Campaign Manager 360 Conversion Feed
hidden: true
intercom_article_id: '10182673'
---

**Prerequisites**

To activate Lifesight’s measurement solution on CM 360, ensure you have the following:

An Advertiser in CM 360

A Floodlight Configuration linked to the above Advertiser

### Setting up Footfall Measurement in CM 360

Follow these steps to start tracking in-store visits in real-time:  
  
1. Create a Floodlight Activity Group

* Go to your Advertiser in CM 360 and navigate to Floodlight > Floodlight Activity Groups.
* Click + Floodlight activity group and name it (e.g., "Lifesight-Visit").
* Enter a unique group tag, such as “lifes0,” and select the Action conversion type.
* Click Save.

2. Create a Floodlight Activity

* In your Advertiser, go to Floodlight > Activities and click New.
* Name the activity (e.g., "Lifesight-Visits") and provide a reference URL.
* Choose the Counter activity type and assign it to the Activity Group you created.
* Select the Standard counting method and save your settings.

3. Share Report Permissions with Lifesight

* Go to Admin > User Profiles > New and enter Lifesight as the name.
* Use the email ls-billing@lifesight.io and ensure the profile has access permissions across the relevant Advertiser.
* Confirm permissions to allow Lifesight to access necessary data.

4. Provide Configuration & Activity IDs to Lifesight

* Share the Floodlight Configuration ID and Floodlight Activity ID with your Lifesight Account Manager to finalize the integration.

5. Set Up the Campaign on the Lifesight Platform

* Navigate to the Measurement module in the Lifesight Platform and select Add New Measurement.
* Choose Measure visitors to my stores from digital campaigns and fill in details like Campaign Name, Campaign Flight, and Attribution Flight.
* Select the Google MP tile, enter the estimated budget and impressions, and enable Conversion Data.
* Provide the Floodlight Activity ID and Lifesight Profile ID (6680657), add locations, and click Add Measurement.
* Reporting on CM 360

To view offline conversions in CM 360, go to your Floodlight reports and select the relevant columns for offline metrics.

For any questions, reach out to platformdelivery@lifesight.io.