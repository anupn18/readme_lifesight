---
title: Click Tracker Implementation Guide
intercom_article_id: '9812990'
---
For all platforms, kindly ensure to add the landing page of your campaign in Lifesight click tracker under Redirect macro. Step 6 in [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **Facebook Implementation:**

### Steps for implementing the Lifesight click tracker in Facebook:

1. Log in Facebook Ads Manager and navigate to the Campaign
2. Go to Ads and find the placeholder “Website URL”
3. Place Lifesight Click Tracker with encoded URL in the “Website URL” placeholder     
    

   ![](https://files.readme.io/95fdbb89a86e6b89188bf2f511a52218807e09fc4741ba07bbdbc80eb9143974-image.png)

   <br />

![](../images/a35f80d6a19efa4425f3e908096fb82c.png)

## **Google Ads, Google Ads (YouTube) and Pmax Implementation:**

Follow these steps to add the trackers:

1. Go to Ads settings.
2. Navigate to Final URL Placeholder

Final URL: Add your creative Landing Page

Example: [https://test.io/](https://test.io/)  

![](https://files.readme.io/f0691702ab1ebd0a09e5a41d33754ea0c42508c965fcf11c531a6ce2beaa003a-image.png)

<br />

3. Navigate to Tracking Template: The Tracking Template is where the third-party click tracker is to be added. This template allows Google Ads to track clicks through the third-party tracker before redirecting the user to the Final URL
4. Paste the Click tracker URL taken from LifeSight UI and add the tracker in the Tracking Template placeholder. Click on the save button.  
   **Example:**  
   [https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=CLICK&crid={'{creative}'}&channel=gads&cv=[cv]&cb=%25%25CACHEBUSTER%25%25&db_redirect=NO&redirect=](https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=CLICK\&crid=%7Bcreative%7D\&channel=gads\&cv=\[cv]\&cb=%25%25CACHEBUSTER%25%25\&db_redirect=NO\&redirect=https%3A%2F%2Ftest.io%2F){'{lpurl}'}

![](../images/f7eee9213b0162c412bbee77cb91e9d0.png)

## **Lifesight Third-Party Click Tracker Implementation in TTD:**

1. Log in to The Trade Desk (TTD):
2. From the dashboard, go to the Campaigns tab and select or create a campaign
3. Under the selected campaign, go to the Creatives section.
4. Under the Tracking section, there will be an option for Click Tracking URL.
5. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

##

## **Xandr Implementation:**

1. Log in to Xandr
2. From the dashboard, go to the Campaigns tab and select or create a campaign
3. Under the selected campaign, go to the Creatives section.
4. In the Creative Setup or Creative Edit page, look for the Click Tracking section.
5. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **Google Ad Manager (GAM) Implementation:**

Kindly follow the below steps for implementing the click tracker.

1. Log in GAM and navigate to the Campaign

2. In GAM, go to the Delivery section and open the relevant Order and select the Line Item where the click tracker will be implemented.

3. Edit the Creative

4. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **Yahoo Implementation:**

1. Log in to Yahoo DSP:
2. From the dashboard, navigate to the Campaigns tab.
3. Select the campaign where you want to add the third-party click tracker or create a new one.
4. Go to the Creatives section under the selected campaign.
5. Choose an existing creative or create a new one.
6. In the Creative Setup page, locate the Click Tracking section.
7. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **X (Twitter) Implementation:**

Kindly follow the below steps for implementing the click tracker.

1. Login to Twitter
2. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns) in the creative section

## **Inmobi Implementation:**

1. Log in to InMobi:
2. From the InMobi dashboard, go to the Campaigns section.
3. Either select an existing campaign or click Create Campaign to start a new one.
4. Within the campaign, go to the Creatives section and select an existing creative or create a new one.
5. In the Creative Setup page, go to the Tracking section.
6. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **Adform Implementation:**

1. Log in to Adform:

2. Go to the Campaigns section in the left-hand sidebar.

3. Either select an existing campaign or create a new campaign by clicking Create Campaign.

4. Inside the campaign, click on Creatives and either select an existing creative or create a new one.

5. In the Tracking section, locate the field for Click Tracking URL.

6. Paste the Click tracker URL taken from Lifesight UI after encoding the Landing page of your campaign as present in Step 6 of [https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns](https://support.lifesight.io/en/articles/9025854-measure-digital-campaigns)

## **Google Campaign Manager (GCM/DCM) Implementation:**

### **Setting Up the Click Event Tag**

Similar to the impression event tag, you can create an event tag for Click event.

Create an Event tag at the DCM campaign level and apply the same to placements you are running.

In DCM >> Campaign >> Properties

![](https://files.readme.io/5efd1c9daf55b6cbfe3eb50e7c993637168262b6d54062974b7a642d58fe0c4a-image.png)

![](../images/ee3aaef1268a9f031dce4567f64dee5e.png)

Copy the Lifesight click tracker till ‘Redirect=‘ as shown below

![](https://files.readme.io/833fefc8a34e18ee5bf53150e3f42939dfaca3023ae264d71d631b8c3b7c2ce3-image.png)

<br />

In the tag settings:

* Set 'Escaping' to 'One level' from the dropdown menu.
* Use your advertiser's landing page URL at the Ad Level directly.    

  <br />

  ![](https://files.readme.io/57cb240fd09468cf7e4d91e9036eaabab486fc3190fd2996d32bcff05c1f3563-image.png)

  <br />

You will be able to view the created impression and click event tag and apply the same at your placement level. Click on the preview of your ad to check if the redirection is landing on the page added.    

![](https://files.readme.io/ca02249e9215126a5dcad6f1c39a961e762cd14c71bf9625975479fe0667dd15-image.png)

<br />

***

If you are facing any difficulty implementing the click tracker, please reach out to us at [platformdelivery@lifesight.io](mailto:platformdelivery@lifesight.io)
