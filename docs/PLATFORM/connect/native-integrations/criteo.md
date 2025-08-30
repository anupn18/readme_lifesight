---
title: '[WIP] Criteo'
excerpt: 'Connect your Criteo account to the platform '
deprecated: false
hidden: true
metadata:
  robots: index
---
Connect your Criteo advertising account to the Lifesight Platform to unlock powerful insights into your campaign performance. This integration ingests your Criteo campaign data, allowing you to analyze performance metrics and measure your true marketing impact within Lifesight's holistic framework. By centralizing your data, you can optimize budget allocation and generate a unified, data-driven view of your Criteo advertising efforts.

<br />

While the integration also facilitates campaign and audience management, its primary benefit is enhancing your analytical capabilities.

Key capabilities include:

1. Performance Analytics: Ingest Criteo campaign data to analyze key metrics like revenue and understand its contribution to your overall marketing mix.
2. Campaign Management: Programmatically toggle the status of your campaigns, ad sets, and ads between ACTIVE and PAUSED.
3. Audience Synchronization: Push Lifesight audience segments to Criteo to create custom audiences for targeted campaigns.

> 📘 Prerequisites
>
> You must have administrative permissions in your Criteo account to authorize third-party application access.

***

### Setup Guide

Follow these steps to connect your Criteo account to Lifesight:

1. **Navigate to Integrations**
   From the main navigation menu on the left, click on the **Integrations** icon.

2. **Locate Criteo**
   On the Integrations page, use the search bar to find "Criteo". It will appear under the "Advertising" category.

   _[Image: Screenshot 2025-08-28 at 12.30.46 PM.png]_

3. **Initiate Connection**
   Click on the Criteo integration card. A pop-up modal will appear. Click the **Connect** button to begin the authorization process.

4. **Authorize Lifesight in Criteo**
   You will be redirected to a Criteo login page. Enter your Criteo credentials to log in and grant Lifesight permission to access your account data.

   > ⚠️ Important
   > The permissions you grant will allow Lifesight to manage campaigns, audiences, and creatives, as well as read analytics and catalog data on your behalf. Please review the permissions screen carefully.
   >
   > _[Image: Screenshot 2025-08-28 at 12.34.20 PM.jpg]_

5. **Select Your Ad Account**
   After authorizing, you will be returned to the Lifesight platform. Select the specific Criteo ad account you wish to connect from the dropdown menu.

   _[Image: Screenshot 2025-08-28 at 12.38.48 PM.jpg]_

6. **Confirm and Finish**
   Click **Connect** to finalize the setup. The Criteo integration will now show as "Active" on your Integrations page.

***

### Integration Capabilities

This integration grants Lifesight specific permissions to manage your Criteo assets:

* **Campaigns (Manage)**: Allows the app to manage your campaigns, including changing bid levels (CPC, CPO target) and status.
* **Audiences (Manage)**: Allows the app to manage your audiences, which is essential for syncing segments from Lifesight.
* **Creatives (Manage)**: Allows the app to manage your creatives.
* **Analytics (Read)**: Allows the app to read analytics data from your campaigns, such as revenue over the last seven days.
* **Catalog (Read)**: Allows the app to read your catalog data.

***

### Troubleshooting

* **Connection Error**: If you encounter an error during the connection process, verify that you are logged into the correct Criteo account and that your account has the necessary permissions to authorize new applications.
* **Incorrect Account Connected**: If you have connected the wrong Criteo ad account, simply disconnect the integration from the Integrations page and repeat the setup process, ensuring you select the correct account in Step 5.