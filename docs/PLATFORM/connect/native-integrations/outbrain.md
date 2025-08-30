---
title: Outbrain
excerpt: Integrate your Outbrain account with Lifesight
deprecated: false
hidden: false
metadata:
  robots: index
---
Outbrain is a leading content discovery and native advertising platform. It helps brands promote content like articles, blog posts, and videos on the open web, placing them on the sites of major online publishers. Ads appear in recommendation feeds, often under labels like "Sponsored Stories," matching the look and feel of the host website to create a non-disruptive user experience.

## Connect your Outbrain Account

Integrate your Outbrain advertising account with the Lifesight Platform to pull spend and performance data automatically. This allows you to measure the impact of your Outbrain campaigns alongside all other marketing channels in a single, unified view.

### Prerequisites

Before you begin, please ensure you have the following:

* An active Outbrain account with administrative privileges.
* Your Outbrain API Key.

> ℹ️ **Finding Your API Key**
>
> You can typically generate or find your API Key within the Outbrain platform. Please refer to [Outbrain API's](https://developer.outbrain.com/home-page/amplify-api/documentation/#/reference/authentications) official documentation for more information.

### Setup Guide

Follow these steps to connect your Outbrain account:

1. From the Lifesight navigation menu, go to **Integrations**.
2. Use the search bar to find and select **Outbrain** from the list of advertising platforms.
3. Click on the Outbrain card to open the connection modal.
4. In the **"Connect to Outbrain"** window, paste your **API Key** into the designated field and click **Connect**.
5. A second window will appear. From the **Select Account** dropdown menu, choose the specific Outbrain advertiser account you wish to connect to the platform.
6. Click **Connect** one final time to authorize the connection.

Once successfully connected, the status of the Outbrain integration will change to **Active** on the Integrations page. The platform will then begin ingesting your data.

<Callout icon="🚧" theme="warn">
  #### _**Token Validity**_

  Outbrain API Token is valid for 30 days. Once you connect your Outbrain account to the Lifesight platform, you need to refresh your outbrain token after 30 days.
</Callout>

### Troubleshooting

<Callout icon="⚠️" theme="warn">
  #### **Invalid API Key**

  If you receive an error after entering your API key, please verify that the key is correct and has not expired. Regenerate the key in your Outbrain account if necessary and try the connection steps again.
</Callout>

<Callout icon="⚠️" theme="warn">
  #### **Account Not Listed**

  If you do not see your expected account in the "Select Account" dropdown, ensure that the API Key you are using has the necessary permissions to access that specific advertiser account within Outbrain.
</Callout>

<br />