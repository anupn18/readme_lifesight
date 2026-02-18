---
title: Impression Tracker Implementation Guide
deprecated: false
hidden: false
metadata:
  robots: index
---
Impression Tracker Implementation Guide
This guide provides instructions for implementing Lifesight Impression trackers across various platforms.

Updated over a year ago

Impression Tracker DV360 Implementation:
In DV360 (Display & Video 360), adding a third-party impression tracker is typically done at the creative level.

Steps to Add Third-Party Impression Tracker in DV360:

1. Log in to DV360

Access your DV360 account and navigate to the relevant campaign.

2. Go to Creatives

From the main navigation panel, select Creatives under the Campaigns section.

3. Select the Creative

Find the creative for which you want to add the third-party tracker. This can be a display, video, or rich media creative and open to the specific creative.

4. Add Third-Party Trackers

Scroll to the section labeled “Tracking”

Look for the field where you can input third-party tracking URLs.

In the Impression tracking field, paste the impression tracker URL taken from LS UI

Example Trackers

​`For Display: <img height="1" width="1" style="border-style:none;" alt="" src="https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN_ID}&crid=${CREATIVE_ID}&db_redirect=NO&app=${SOURCE_URL_ENC}" />`

For Video: [https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=$\{CACHEBUSTER}&cid=$\{CAMPAIGN_ID}&crid=$\{CREATIVE_ID}&db_redirect=NO&app=$\{SOURCE_URL_ENC}](https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER\&channel=dv360\&cv=\[cv]\&cachebuster=$\{CACHEBUSTER}\&cid=$\{CAMPAIGN_ID}\&crid=$\{CREATIVE_ID}\&db_redirect=NO\&app=$\{SOURCE_URL_ENC})

5. Save Changes

Once the tracker is added, save the creative

The Trade Desk Implementation:
Steps to Implement:

Log in to The Trade Desk (TTD).

Choose an existing campaign or create a new one.

Click on Creative in the campaign setup options.

If you are creating a new creative, click New Creative. If you want to add an impression tracker to an existing creative, select the creative and click Edit.

In the Creative setup page, you will see an option for Tracking.

Under Tracking, there is an option to add an Impression Tracking URL.

Paste the impression tracker URL taken from LS UI

Xandr Implementation:
Log in to Xandr:

Choose an existing campaign or create a new one.

Under the selected campaign, go to the Creatives tab.

In the Creative Setup or Creative Edit page, find the section for Tracking. Look for the option to add an Impression Tracking URL or Third-Party Impression Tracker.

Paste the impression tracker URL taken from LS UI

Google Ad Manager Implementation:

1. Locate the Placement for Tracking by navigating to the Inventory section in GAM. Identify the ad unit or placement where the impression tracker needs to be added.

2. Edit the Ad Unit or Line Item

3. Go to the Line Items tab associated with the campaign. Open the specific line item where you want to implement the impression tracker.

4. In the Creatives section of the line item, locate the creative you want to track.

Open the creative settings and find the Tracking URL or Impression Tracking URL field.

5. Paste the impression tracker URL taken from LS UI.

Yahoo DSP Implementation:
Log in to Yahoo DSP:

From the dashboard, click on the Campaigns tab to view and manage your campaigns.

Under the Creatives section of the campaign, either create a new creative or select an existing creative you wish to add the impression tracker to.

Within the creative setup, locate the Tracking section.

Paste the impression tracker URL taken from LS UI

Inmobi Implementation:
Log in to InMobi:

From the InMobi dashboard, go to the Campaigns section.

Either select an existing campaign or click Create Campaign to create a new one.

In the Creative Setup page, locate the Tracking section. This is where you can add third-party tracking URLs.

Paste the impression tracker URL taken from LS UI

Adform Implementation:
Log in to Adform:

Either select an existing campaign or click on Create Campaign to start a new one.

In the Creative section of the campaign, click on Add Creative or select an existing creative to edit.

In the Tracking section of the creative setup, you'll find options for third-party trackers.

Paste the impression tracker URL taken from LS UI

Google Campaign Manager (GCM/DCM) Implementation:

Integrating DCM (DoubleClick Campaign Manager) with the Lifesight Pixel is a crucial step for ensuring accurate tracking of your digital campaigns. This guide provides a detailed, step-by-step process to help you set up event tags for both impressions and clicks within DCM, allowing Lifesight to capture the necessary data for your campaigns.

1. Setting Up the Impression Event Tag
   Create an Event tag at the DCM campaign level and apply the same to placements you are running

In DCM >> Campaign >> Properties

Lifesight Impression Tracker example:

`[https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=RENDER&channel=gmp&cv=[cv]&cachebuster=$\{CACHEBUSTER}&cid=$](https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=RENDER&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN_ID}&crid=${CREATIVE_ID}&db_redirect=NO&app=${SOURCE_URL_ENC}`

Add the impression event tag properties and save.

You will be able to see the tracker added onto DCM.

Adobe Advertising Implementation:
Log in to Adobe DSP:

From the dashboard, click on the Campaigns tab to view

Navigate to the Creative Settings or Ad Tracking Section during campaign setup.

Paste the impression tracker URL taken from LS UI

Amobee Implementation:
Log in to Amobee DSP:

From the dashboard, click on the Campaigns tab to view

During Campaign Creation, in the Third-Party Tracking or Impression Tracking URL section.

This is usually found in the creative upload or tracking tab.

Paste the impression tracker URL taken from LS UI

Digital Turbine Implementation:
Log in to Digital Turboline DSP:

From the dashboard, click on the Campaigns tab to view

During Creative Setup, look for a field labeled Impression Tracking URL or Third-Party Trackers.

Paste the impression tracker URL taken from LS UI

SpotAd Implementation:
Log in to SpotAd DSP:

From the dashboard, click on the Campaigns tab to view

In the Ad or Campaign Tracking Section during campaign setup or creative upload.

Look for a field labeled Impression Tracking Pixel or Third-Party Tracking.

Paste the impression tracker URL taken from LS UI

Affle Implementation:
Log in to Affle DSP:

From the dashboard, click on the Campaigns tab to view

During the Creative Setup, locate the Third-Party Tracking URL section.

Paste the impression tracker URL taken from LS UI

Quantcast Implementation:
Log in to Quantcast DSP:

From the dashboard, click on the Campaigns tab to view

In the Creative Tracking Section, Paste the impression tracker URL taken from LS UI.

Kargo Implementation:
Log in to Kargo DSP:

From the dashboard, click on the Campaigns tab to view

During Creative Upload, locate the Third-Party Tracking Pixel field.

Paste the impression tracker URL taken from LS UI.

StackAdapt Implementation:
Log in to StackAdapt DSP:

From the dashboard, click on the Campaigns tab to view

In the Creative Settings during campaign creation.

In the Third-Party Impression Tracking URL field, Paste the impression tracker URL taken from LS UI.

TikTok Implementation:
Log in to TikTok DSP:

From the dashboard, click on the Campaigns tab to view

When setting up a creative under an ad group in TikTok Ads Manager , scroll down to "Third party tracking settings".

Paste the impression tracker URL taken from LS UI

Crimtan Implementation:
Log in to Crimtan DSP:

From the dashboard, click on the Campaigns tab to view

During campaign or creative setup, look for the Impression Tracking or Third-Party Tracking field.

Paste the impression tracker URL taken from LS UI

Consult Crimtan support if specific instructions are needed.

***

If you are facing any difficulty implementing the click tracker, please reach out to us at [platformdelivery@lifesight.io](mailto:platformdelivery@lifesight.io)
