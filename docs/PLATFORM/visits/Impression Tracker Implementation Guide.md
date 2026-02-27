---
title: "Impression Tracker Implementation Guide"
intercom_article_id: "10398357"
---

## **Impression Tracker DV360 Implementation:**

In DV360 (Display & Video 360), adding a third-party impression tracker is typically done at the creative level.

Steps to Add Third-Party Impression Tracker in DV360:

1) Log in to DV360

Access your DV360 account and navigate to the relevant campaign.

2) Go to Creatives

From the main navigation panel, select Creatives under the Campaigns section.

3) Select the Creative

Find the creative for which you want to add the third-party tracker. This can be a display, video, or rich media creative and open to the specific creative.

4) Add Third-Party Trackers

* Scroll to the section labeled “Tracking”
* Look for the field where you can input third-party tracking URLs.
* In the Impression tracking field, paste the impression tracker URL taken from LS UI

**Example Trackers**

​For Display: <img height="1" width="1" style="border-style:none;" alt="" src="[https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}"/](https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=$%7BCACHEBUSTER%7D&cid=$%7BCAMPAIGN_ID%7D&crid=$%7BCREATIVE_ID%7D&db_redirect=NO&app=$%7BSOURCE_URL_ENC%7D%22/)>

For Video: [https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}](https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=$%7BCACHEBUSTER%7D&cid=$%7BCAMPAIGN_ID%7D&crid=$%7BCREATIVE_ID%7D&db_redirect=NO&app=$%7BSOURCE_URL_ENC%7D)

5) Save Changes

Once the tracker is added, save the creative

## **The Trade Desk Implementation:**

Steps to Implement:

1. Log in to The Trade Desk (TTD).
2. Choose an existing campaign or create a new one.
3. Click on Creative in the campaign setup options.
4. If you are creating a new creative, click New Creative. If you want to add an impression tracker to an existing creative, select the creative and click Edit.
5. In the Creative setup page, you will see an option for Tracking.
6. Under Tracking, there is an option to add an Impression Tracking URL.
7. Paste the impression tracker URL taken from LS UI

## **Xandr Implementation:**

1. Log in to Xandr:
2. Choose an existing campaign or create a new one.
3. Under the selected campaign, go to the Creatives tab.
4. In the Creative Setup or Creative Edit page, find the section for Tracking. Look for the option to add an Impression Tracking URL or Third-Party Impression Tracker.
5. Paste the impression tracker URL taken from LS UI

## **Google Ad Manager Implementation:**

1. Locate the Placement for Tracking by navigating to the Inventory section in GAM. Identify the ad unit or placement where the impression tracker needs to be added.

2. Edit the Ad Unit or Line Item

3. Go to the Line Items tab associated with the campaign. Open the specific line item where you want to implement the impression tracker.

4. In the Creatives section of the line item, locate the creative you want to track.

Open the creative settings and find the Tracking URL or Impression Tracking URL field.

5. Paste the impression tracker URL taken from LS UI.

## **Yahoo DSP Implementation:**

1. Log in to Yahoo DSP:
2. From the dashboard, click on the Campaigns tab to view and manage your campaigns.
3. Under the Creatives section of the campaign, either create a new creative or select an existing creative you wish to add the impression tracker to.
4. Within the creative setup, locate the Tracking section.
5. Paste the impression tracker URL taken from LS UI

## **Inmobi Implementation:**

1. Log in to InMobi:
2. From the InMobi dashboard, go to the Campaigns section.
3. Either select an existing campaign or click Create Campaign to create a new one.
4. In the Creative Setup page, locate the Tracking section. This is where you can add third-party tracking URLs.
5. Paste the impression tracker URL taken from LS UI

## **Adform Implementation:**

1. Log in to Adform:
2. Either select an existing campaign or click on Create Campaign to start a new one.
3. In the Creative section of the campaign, click on Add Creative or select an existing creative to edit.
4. In the Tracking section of the creative setup, you'll find options for third-party trackers.
5. Paste the impression tracker URL taken from LS UI

## **Google Campaign Manager (GCM/DCM) Implementation:**

Integrating DCM (DoubleClick Campaign Manager) with the Lifesight Pixel is a crucial step for ensuring accurate tracking of your digital campaigns. This guide provides a detailed, step-by-step process to help you set up event tags for both impressions and clicks within DCM, allowing Lifesight to capture the necessary data for your campaigns.

## **1. Setting Up the Impression Event Tag**

Create an Event tag at the DCM campaign level and apply the same to placements you are running

**In DCM >> Campaign >> Properties**

![](../images/d2c4d95c24b89f38f770b42f6cfb92cb.png)

![](../images/f4b1a48de004822c32571968303a529c.png)

**Lifesight Impression Tracker example:**

**[https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=RENDER&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=$](https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=RENDER&channel=gmp&cv=[cv]&cachebuster=$%7BCACHEBUSTER%7D&cid=$) {CAMPAIGN\_ID}&crid=${CREATIVE\_ID}&db\_redirect=NO&app=${SOURCE\_URL\_ENC}**

![](../images/ac210c289a186603ab1e1f70a80b831f.png)

Add the impression event tag properties and save.

![](../images/977af29c2fb8d5e9853bcf83e04399fb.png)

You will be able to see the tracker added onto DCM.

![](../images/7c0e3ea015b10abe62faf234871dd4ca.png)

## **Adobe Advertising Implementation:**

1. Log in to Adobe DSP:
2. From the dashboard, click on the Campaigns tab to view
3. Navigate to the Creative Settings or Ad Tracking Section during campaign setup.
4. Paste the impression tracker URL taken from LS UI

## **Amobee Implementation:**

1. Log in to Amobee DSP:
2. From the dashboard, click on the Campaigns tab to view
3. During Campaign Creation, in the Third-Party Tracking or Impression Tracking URL section.
4. This is usually found in the creative upload or tracking tab.
5. Paste the impression tracker URL taken from LS UI

## **Digital Turbine Implementation:**

1. Log in to Digital Turboline DSP:
2. From the dashboard, click on the Campaigns tab to view
3. During Creative Setup, look for a field labeled Impression Tracking URL or Third-Party Trackers.
4. Paste the impression tracker URL taken from LS UI

## **SpotAd Implementation:**

1. Log in to SpotAd DSP:
2. From the dashboard, click on the Campaigns tab to view
3. In the Ad or Campaign Tracking Section during campaign setup or creative upload.
4. Look for a field labeled Impression Tracking Pixel or Third-Party Tracking.
5. Paste the impression tracker URL taken from LS UI

## Affle Implementation:

1. Log in to Affle DSP:
2. From the dashboard, click on the Campaigns tab to view
3. During the Creative Setup, locate the Third-Party Tracking URL section.
4. Paste the impression tracker URL taken from LS UI

## **Quantcast Implementation:**

1. Log in to Quantcast DSP:
2. From the dashboard, click on the Campaigns tab to view
3. In the Creative Tracking Section, Paste the impression tracker URL taken from LS UI.

## **Kargo Implementation:**

1. Log in to Kargo DSP:
2. From the dashboard, click on the Campaigns tab to view
3. During Creative Upload, locate the Third-Party Tracking Pixel field.
4. Paste the impression tracker URL taken from LS UI.

## **StackAdapt Implementation:**

1. Log in to StackAdapt DSP:
2. From the dashboard, click on the Campaigns tab to view
3. In the Creative Settings during campaign creation.
4. In the Third-Party Impression Tracking URL field, Paste the impression tracker URL taken from LS UI.

## **TikTok Implementation:**

1. Log in to TikTok DSP:
2. From the dashboard, click on the Campaigns tab to view
3. When setting up a creative under an ad group in TikTok Ads Manager , scroll down to "Third party tracking settings".

![](../images/4b13ab2ffceeceab9f9a0e0039c6e7ac.png)

Paste the impression tracker URL taken from LS UI

## **Crimtan Implementation:**

1. Log in to Crimtan DSP:
2. From the dashboard, click on the Campaigns tab to view
3. During campaign or creative setup, look for the Impression Tracking or Third-Party Tracking field.
4. Paste the impression tracker URL taken from LS UI
5. Consult Crimtan support if specific instructions are needed.

-------

If you are facing any difficulty implementing the click tracker, please reach out to us at platformdelivery@lifesight.io