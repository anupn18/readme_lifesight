---
title: Impression Tracker Implementation Guide
excerpt: >-
  This guide provides instructions for implementing Lifesight Impression
  trackers across various platforms.
deprecated: false
hidden: true
metadata:
  robots: index
---
<br />

# Impression Tracker Implementation Guide

Integrating various platforms with the Lifesight Pixel is a crucial step for ensuring accurate tracking of your digital campaigns. This guide provides a detailed, step-by-step process to help you set up impression trackers across multiple DSPs and Ad Servers.

### **Impression Tracker DV360 Implementation**

In DV360 (Display & Video 360), adding a third-party impression tracker is typically done at the creative level.

1. **Log in to DV360:** Access your DV360 account and navigate to the relevant campaign.
2. **Go to Creatives:** From the main navigation panel, select Creatives under the Campaigns section.
3. **Select the Creative:** Find the creative for which you want to add the third-party tracker. This can be a display, video, or rich media creative and open to the specific creative.
4. **Add Third-Party Trackers:**
   * Scroll to the section labeled “Tracking”.
   * Look for the field where you can input third-party tracking URLs.
   * In the Impression tracking field, paste the impression tracker URL taken from LS UI.
   * **Example Trackers:**
     * **For Display:** `<img height="1" width="1" style="border-style:none;" alt="" src="https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN_ID}&crid=${CREATIVE_ID}&db_redirect=NO&app=${SOURCE_URL_ENC}"/>`
     * **For Video:** `https://pixel.ad.lifesight.io/pixel/event/BYL72R?event=RENDER&channel=dv360&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN_ID}&crid=${CREATIVE_ID}&db_redirect=NO&app=${SOURCE_URL_ENC}`
5. **Save Changes:** Once the tracker is added, save the creative.

***

### **The Trade Desk Implementation**

1. **Log in to The Trade Desk (TTD):** Access your account.
2. **Select Campaign:** Choose an existing campaign or create a new one.
3. **Go to Creative:** Click on Creative in the campaign setup options.
4. **Select Creative:** If you are creating a new creative, click New Creative. If you want to add an impression tracker to an existing creative, select the creative and click Edit.
5. **Add Tracking:** In the Creative setup page, you will see an option for Tracking.
6. **Input URL:** Under Tracking, there is an option to add an Impression Tracking URL.
7. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Xandr Implementation**

1. **Log in to Xandr:** Access your account.
2. **Select Campaign:** Choose an existing campaign or create a new one.
3. **Go to Creatives:** Under the selected campaign, go to the Creatives tab.
4. **Add Tracking:** In the Creative Setup or Creative Edit page, find the section for Tracking. Look for the option to add an Impression Tracking URL or Third-Party Impression Tracker.
5. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Google Ad Manager Implementation**

1. **Locate Placement:** Locate the Placement for Tracking by navigating to the Inventory section in GAM. Identify the ad unit or placement where the impression tracker needs to be added.
2. **Edit Line Item:** Go to the Line Items tab associated with the campaign. Open the specific line item where you want to implement the impression tracker.
3. **Select Creative:** In the Creatives section of the line item, locate the creative you want to track.
4. **Add Tracking:** Open the creative settings and find the Tracking URL or Impression Tracking URL field.
5. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Yahoo DSP Implementation**

1. **Log in to Yahoo DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view and manage your campaigns.
3. **Select Creative:** Under the Creatives section of the campaign, either create a new creative or select an existing creative you wish to add the impression tracker to.
4. **Add Tracking:** Within the creative setup, locate the Tracking section.
5. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Inmobi Implementation**

1. **Log in to InMobi:** Access your account.
2. **Go to Campaigns:** From the InMobi dashboard, go to the Campaigns section.
3. **Select Campaign:** Either select an existing campaign or click Create Campaign to create a new one.
4. **Add Tracking:** In the Creative Setup page, locate the Tracking section. This is where you can add third-party tracking URLs.
5. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Adform Implementation**

1. **Log in to Adform:** Access your account.
2. **Select Campaign:** Either select an existing campaign or click on Create Campaign to start a new one.
3. **Select Creative:** In the Creative section of the campaign, click on Add Creative or select an existing creative to edit.
4. **Add Tracking:** In the Tracking section of the creative setup, you'll find options for third-party trackers.
5. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Google Campaign Manager (GCM/DCM) Implementation**

1. **Navigate to Properties:** In DCM >> Campaign >> Properties.    

   <br />

   ![](https://files.readme.io/d039a639c539bfd5f4a986709d14c6669b7d359a89294fdc65ff5641e1d11440-image.png)

     
     

   ![](https://files.readme.io/94f1e73460b356554fa86c80b6f517c4de968a9a64689a1ebc166514a6690cd3-image.png)

   <br />
2.   **Set Up Event Tag:** Create an Event tag at the DCM campaign level and apply the same to placements you are running.
3. **Lifesight Impression Tracker example:** `https://pixel.ad.lifesight.io/pixel/event/XXXXXX?event=RENDER&channel=gmp&cv=[cv]&cachebuster=${CACHEBUSTER}&cid=${CAMPAIGN_ID}&crid=${CREATIVE_ID}&db_redirect=NO&app=${SOURCE_URL_ENC}`  

   ![](https://files.readme.io/7bcd5444e510ffd996f962613518e6e28efd91eadc95f7f7a3277736e8c25648-image.png)
4. **Save Properties:** Add the impression event tag properties and save.  

   ![](https://files.readme.io/ac75c474e049d5aa1fa652198108452a5399c090adee5fd6c017a0d6ac2aceda-image.png)

   <br />
5. **Verify:** You will be able to see the tracker added onto DCM.

***

### **Adobe Advertising Implementation**

1. **Log in to Adobe DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** Navigate to the Creative Settings or Ad Tracking Section during campaign setup.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Amobee Implementation**

1. **Log in to Amobee DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** During Campaign Creation, in the Third-Party Tracking or Impression Tracking URL section. This is usually found in the creative upload or tracking tab.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Digital Turbine Implementation**

1. **Log in to Digital Turbine DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** During Creative Setup, look for a field labeled Impression Tracking URL or Third-Party Trackers.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **SpotAd Implementation**

1. **Log in to SpotAd DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** In the Ad or Campaign Tracking Section during campaign setup or creative upload. Look for a field labeled Impression Tracking Pixel or Third-Party Tracking.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Affle Implementation**

1. **Log in to Affle DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** During the Creative Setup, locate the Third-Party Tracking URL section.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **Quantcast Implementation**

1. **Log in to Quantcast DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** In the Creative Tracking Section, paste the impression tracker URL taken from LS UI.

***

### **Kargo Implementation**

1. **Log in to Kargo DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** During Creative Upload, locate the Third-Party Tracking Pixel field.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

***

### **StackAdapt Implementation**

1. **Log in to StackAdapt DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** In the Creative Settings during campaign creation. In the Third-Party Impression Tracking URL field, paste the impression tracker URL taken from LS UI.

***

### **TikTok Implementation**

1. **Log in to TikTok DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** When setting up a creative under an ad group in TikTok Ads Manager, scroll down to "Third party tracking settings".
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.

![](https://files.readme.io/e799da0e038d736f0de0794061c00d257d4e0964259766b2b099ee11d3acd897-image.png)

<br />

***

### **Crimtan Implementation**

1. **Log in to Crimtan DSP:** Access your account.
2. **View Campaigns:** From the dashboard, click on the Campaigns tab to view.
3. **Add Tracking:** During campaign or creative setup, look for the Impression Tracking or Third-Party Tracking field.
4. **Paste Tracker:** Paste the impression tracker URL taken from LS UI.
5. **Support:** Consult Crimtan support if specific instructions are needed.

***

If you are facing any difficulty implementing the click tracker, please reach out to us at [platformdelivery@lifesight.io](mailto:platformdelivery@lifesight.io)

<br />
