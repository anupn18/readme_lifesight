---
title: Snapchat CAPI
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## What is Snapchat Conversions API?

Snap’s Conversions API (CAPI) is a structured, privacy-centric interface that allows advertisers to pass conversion events to Snap via a Server-to-Server (S2S) integration. This helps Snapchat to optimize their ad campaigns, improve their targeting and measure the conversions that resulted from Snapchat campaigns.  

<br />

## Benefits of using the Snapchat CAPI

- Emphasis on Privacy:The Conversions API prioritizes privacy, offering you the ability to selectively share data at your discretion.
- Enhanced Optimization: The data provided to Snapchat through the Conversions API enhances the efficiency and effectiveness of your campaign strategies, leading to more cost-effective actions.
- Targeting Capabilities: With the Conversions API, you can swiftly create custom audiences using first-party data, enabling the formation of Lookalike audiences or re-engaging previous customers.
- Sophisticated Measurement: The Conversions API facilitates a deeper understanding of your campaign's impact across various channels, integrating advanced measurement methods like Conversion Lift for more nuanced insights.

<br />

## Prerequisites to setting up the Snapchat CAPI

To set up your CAPI, you will need the following fields from your Snapchat account: 

1. Snapchat Pixel ID:
2. Pixel ID To locate the code:
3. Go to Pixels on your Snapchat account
4. Select the toggle between live events
5. Copy and store the pixel ID that is not being implemented on the website or any platform. If there isn’t any such pixel ID, the user can create a new pixel ID. (Please note to disable the pixel from the website to avoid duplication.)

<br />

## Conversion API Token:

Your Snapchat Access Token is a unique string used to authenticate graph API calls. To locate it:

1. Head to the Business Dashboard
2. Head to Business details
3. Scroll to the section titled ‘Conversions API Token’, click Generate Access Token, and copy the generated Access Token.
4. Store the token for further use

<br />

## Setting up the Snapchat Conversions API

1. Head to Integrations in your left-hand menu.
2. Use the native Snapchat integration to connect your Snapchat ad account with your Lifesight workspace. (Here’s how you can integrate Snapchat.)
3. Click on the integration you’ve just activated. Feed in your Snapchat Pixel ID and the Access Token in the dedicated fields.
4. Turn on the toggle titled ‘Go Live’ and select Save.
5. Your Snapchat conversions API is now live and actively enriching your audience & optimizing your ad costs.

<br />

## Events passed using the Snapchat CAPI

When setting up the Snapchat CAPI, Lifesight passes some events on to the channel as default data points, with an option to add more. The comprehensive list is as below:

1. PURCHASE
2. ADD_CART
3. VIEW_CONTENT
4. PAGE_VIEW
5. CUSTOMER_Registered