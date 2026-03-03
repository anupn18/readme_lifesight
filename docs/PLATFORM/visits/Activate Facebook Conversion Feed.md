---
title: Activate Facebook Conversion Feed
hidden: true
intercom_article_id: '9351690'
---

This guide will walk you through the process of activating and setting up Lifesight's real-time footfall measurement solution on Facebook.  
​  
​

Prerequisites:

To activate Lifesight’s Measurement solution on Facebook, we’ll need the following details:

* Ad Account ID
* List of locations/stores to monitor (Recommended at least 10 stores)
* Minimum of 3Mn Ad impressions volume expected
* Dataset ID

Lifesight will run a feasibility check with all the locations provided in order to confirm the required volume needed will be met.​

## **How to setup Footfall Measurement on Facebook**

Below are the steps you need to take to begin measuring in-store visits in real-time:

1. Lifesight will assist in creating the offline data set.

2. Assign an Ad Account to the offline data set, you can do that by the following steps:

Steps to create and link new dataset for offline event set : -

Login to Meta account >> Navigate to the required Ad account where you want to create the dataset.

1. Click connect data sources.
2. Select the offline option from the pop up window.  
   ​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

3. Give the name to the new data set. Click create.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

4. In the next pop up window, select option I don’t have a website. Click continue  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

5. Select do it yourself in the setup method popup window. Click next  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​6. Select Meta pixel and conversion API option. Click next.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​7.Select set up with partner integration. Click next  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

8.Don’t choose any partner. Click close button.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

9.Created data source will be reflecting under data sources for that add account.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

10.Please make sure the created dataset id is shared with Lifesight business manager.

Lifesight Business manager ID : **270079023746392**  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​

11. Assign the ad account to the created Dataset ID.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​  
12. Use the created dataset ID in the Lifesight platform, in the event ID placeholder for that brand campaign.  
​

![](../images/e344b727f1a463528e04a329aa0b316e.png)

​***Note : if you are running 2 regional specific campaign ( e.g.: AU & NZ ), need to create a two separate dataset ID’s with the proper naming convention.***  
​  
​

------------

After completing the above steps, notify the Lifesight team to add “**LS Billing”** to the dataset. Once the Lifesight team confirms that “**LS Billing”** has been added, please proceed with the following steps:

**1. Verify Dataset Tagging**: Ensure the dataset is tagged correctly within your campaigns in Ads Manager.

Go to Campaign -> Adsets -> Ads

Check the Offline Data set ID is enabled

![](../images/b0b77c09b14eb15f50875ca88f2abe97.png)

**2. Dataset Selection**: Navigate to **Business Settings > Data Sources > Datasets** and verify that the appropriate dataset is selected.  
​

**3. Review Permissions**: Go to **Dataset > People** and enable the permissions “Manage Datasets”

![](../images/5f4ee44872e1f9223eece9f4d8f8c202.png)

4. Save the Datasets

​**Please note: A separate dataset must be created for each campaign individually**

### How to Verify custom events in Meta Events Manager

To review custom events in Meta Events Manager:

![](../images/d3d1e1b9f9ca284973396ede663220e7.png)

1. Go to **Meta Events Manager.**
2. Click the **Data sources** icon in the left menu of the page.
3. Select the name and ID of your data.
4. Click the **Settings** tab at the top of the page.
5. Scroll down to **Data restrictions**.
6. In the **Manage custom event blocking** section, click **Review**.
7. In the **Action required** tab, select all of the custom events that you want to confirm or block. **Note:** You may not be able to confirm custom events that Meta has detected may contain potentially prohibited information.
8. Click **Next**.
9. Select **Confirm the custom event** or **Block the custom event**.
10. Click **Review**. A message will appear on screen if you've successfully confirmed or blocked custom events.
11. Click **Done**.  
    ​

### **Reporting on Facebook**

In order to see the visits, you need to go to [Ads Manager](https://www.facebook.com/ads/manager).

* Select Campaigns, Ads sets or Ads, depending on the results that you want to view.  
  ​
* By default, Lifesight will upload the visits as “Other” type.  
  ​  
   You can select the Columns drop-down menu and choose **Offline conversions** to see your offline conversion reporting.  
  ​

  ![](../images/e344b727f1a463528e04a329aa0b316e.png)

  ​

  ![](../images/e344b727f1a463528e04a329aa0b316e.png)

* You can adjust your attribution window on the bottom-right corner by selecting **Windows Comparison**.  
  ​
* To save this customized selection as a preset for future use, you can tick the **Save as preset box** in the bottom-left corner and enter a name for the preset.

We kindly ask you to setup an automated impressions report to Lifesight ([platformdelivery@lifesight.io](mailto:platformdelivery@lifesight.io)).

Any further questions reach out to : **[platformdelivery@lifesight.io](mailto:platformdelivery@lifesight.io)**