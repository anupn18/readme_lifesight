---
title: '[WIP] Lifesight Tracking Pixel'
deprecated: false
hidden: true
metadata:
  robots: index
---
The Lifesight Tracking Pixel, referred to as **Custom JS** in the platform, is a critical component for understanding user behavior on your website. It is a smart JavaScript snippet that, once installed, identifies and tracks user activities and touchpoints.

This is a foundational step for enabling attribution and measurement on the Lifesight UMM Platform.

### Before You Begin

To complete the installation, you will need one of the following:

* **For the GTM method**: Administrator access to your website's Google Tag Manager (GTM) account.

* **For the Manual method**: The ability to add JavaScript code to the section of your website's HTML source code.

### Step-by-Step Installation Guide

#### 1. Locating the Custom JS Integration

<br />

First, you need to find the Custom JS integration within the Lifesight platform.

1. Log in to your Lifesight UMM Platform account.
2. Navigate to **Integrations** from the main menu on the left.
3. In the search bar, type Custom JS.
4. Click on the **Custom JS** card to begin the setup process.
   <br />
   *\[Screenshot of searching for "Custom JS" in the Integrations section]*
   <br />

#### 2) Choosing Your Setup Method

After clicking the card, a setup window will appear for your website, \{\{YOUR\_WEBSITE\_DOMAIN}}. You have two options for installing the tracking pixel.

<br />

*\[Screenshot of the "Choose Your setup" popup window]*

<br />

We will cover both methods in the following sections.

<br />

### Option A: Google Tag Manager (Recommended)

<br />

This is the fastest and the recommended method to install the tracking chip. It uses a pre-built Google Tag Manager container with all the necessary tags, triggers, and variables for common tracking needs.

1. In the setup window, select the **Import Custom JS GTM Container** option.
2. Click the **Download Custom JS Container** button to save the container.json file to your computer.
3. Open your **Google Tag Manager** account in a new tab.
4. Navigate to the **Admin** section of your GTM container.
5. Under the *Container* column, click on **Import Container**.
6. Click **Choose container file** and select the file you downloaded from Lifesight.
7. Choose the **Workspace** you want to import into (typically 'Default Workspace').
8. Select the **Merge** import option, and then choose **Overwrite conflicting tags, triggers and variables**. This will update your existing setup without removing your current tags.
9. Review the import preview and click **Confirm**.
10. Finally, click **Submit** and then **Publish** in your GTM workspace to make the changes live on your site.
    <br />
    *\[Screenshot of the GTM setup instructions in the Lifesight UI]*
    <br />

### Option B: Manual JavaScript Setup

<br />

Choose this method if you do not use Google Tag Manager or if you need to create custom configurations within an existing GTM setup.

1. In the setup window, select the **Manual Setup** option.
   2. A JavaScript code snippet will be displayed in a text box.
      3. JavaScript(function (measurement) \{ var script =measurement.createElement('script'); script.setAttribute('src','[https://storage.googleapis.com/measure-insight/measureinsight.min.js');script.setAttribute('async](https://storage.googleapis.com/measure-insight/measureinsight.min.js')', ''); measurement.head.appendChild(script); })(document);
   <br />
   4. Paste this snippet into the HTML source code of your website. It must be placed before the closing tag on **every page** you wish to track.
   <br />
   > **Warning**Placing this script in the footer or body of your HTML may lead to incomplete data collection, as it may not load in time to capture all user activity.
   <br />
   *\[Screenshot of the Manual Setup instructions and code snippet in the Lifesight UI]*
   <br />

### Verifying Your Installation

<br />

After installing the pixel using either method, you can verify that it is loading correctly on your website.

1. Open your website in a new browser tab.
   2. Open your browser's Developer Tools (Right-click on the page and select **Inspect**).
      3. Navigate to the **Network** tab within the tools.
         4. In the filter/search box for the network requests, type measureinsight.
            5. Refresh your webpage.
               6. You should see measureinsight.min.js appear in the list with a status code of 200, which indicates it has loaded successfully.
   <br />
   *\[Screenshot of the browser's Network tab showing the script loading successfully]*
   <br />

### Frequently Asked Questions (FAQ)

<br />

\*\*Q: Which installation method should I choose?\*\*A: We strongly recommend the **Google Tag Manager (GTM) Container** method for most users. It's faster, less error-prone, and includes a comprehensive set of pre-configured tracking tags. Choose the Manual Setup only if you do not use GTM or have highly specific custom requirements.

<br />

\*\*Q: What data does the tracking pixel collect?\*\*A: The pixel is designed to collect anonymous and first-party data about user interactions on your website, such as page views, session information, and referral sources. This data is essential for powering Lifesight's attribution models.

<br />

\*\*Q: How long does it take for data to appear in Lifesight?\*\*A: Once the pixel is installed and verified, you should begin to see data populating in your Lifesight dashboards within a few hours. However, please allow up to 24 hours for the initial data to be fully processed and reflected.