---
title: Linkedin CAPI
excerpt: >-
  Learn how to enrich your data on Linkedin and reduce customer acquisition
  costs.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The TikTok conversions API connects an advertisers marketing data from different sources to TikTok. This data is used for conversion optimization and retargeting of ads to the right people. These enhanced events help drive a higher ROAS ad reduce CPC, CPM for advertisers on TikTok.

## Benefits of using the TikTok CAPI

The TikTok CAPI receives both front end and back end events, whereas the pixel often captures events only from the front end. This reduces any data gaps while enriching ad audience and targeting data.

With Lifesight’s Shopify SDK, the back-end events from Shopify stores and associated integrations (reviews, subscription additions, add to wishlist etc.) are captured more accurately and sent to TikTok to enrich the ad sets.

You can further enrich the data using the contact’s attributes which are recorded via Lifesight’s First-Party Identity Graph.

## Pre-requisites to setting up the TikTok CAPI

In order to set up your CAPI, you will need the following from your TikTok account

1. TikTok Pixel that is connected to the website and its Pixel ID
2. An API access token

The below section will walk you through the process of finding those in the Events Manager on TikTok.

> 📘 ## Setting up your TikTok pixel
> 
> In case you haven’t set up a TikTok pixel already, here’s how you can get started:
> 
> Go to TikTok Ads manager
> 
> After logging in, hover over "Tools" on the navigation bar, and find "Management", then click on "Events".
> 
> Click on the "Manage" button under "Web Events".
> 
> Click on the "Partner setup" button under "Web Events".  
> Note: Selecting Partner Setup takes you to a page where you can select different supported TikTok partners for your integration, such as Shopify and Google Tag Manager. You will be able to see Lifesight as one of the Partners under CDP.
> 
> Click on the "Lifesight" to set up the Pixel integration.
> 
> Create an overarching Pixel Name that will hold events regardless of the integration method you end up selecting later on (namely, Pixel, Events API). Make sure to give your pixel a name- The maximum character length is 128 characters, including spaces.

<br />

## Locating the TikTok Pixel ID

If you have already had a pixel created and have Pixel ID and Events API Access Token, skip this step and jump to the Lifesight section.

1. Login to your TikTok Business account and navigate to Tools
2. Head to Events > Web Events > select a pixel > Settings tab.
3. At the top, you will find your Pixel ID. Copy and save the Pixel ID.

​

![](https://files.readme.io/692d9cd-image.png)

## Locating your TikTok API Access Token

1. In the same window as your 'Settings' scroll down to click "Generate Access Token". 

![](https://files.readme.io/2a6c714-image.png)

<br />

2. Copy and save the token information shown.

![](https://files.readme.io/90ce3e6-image.png)

<br />

Now, you should have both your Pixel ID and Access Token. For example, they should look like the following:

> Pixel ID: CKBJ113C77UA008MM2H0
>
> Access Token: 7aea389xxxxxxxxxxxxxxxxxxxxxxxx1991af

You can head over to Lifesight now to finish the rest of the steps to set up the Tiktok Integration in Lifesight Integrations module.

<br />

## Steps to configure the events API on Lifesight

### Set up the TikTok Authentication and Ad Account

In the Integrations module on Lifesight search for Tiktok integration and click on Connect.

![](https://files.readme.io/1cccfa0-image.png)

<br />

Once you have finished authentication for your TikTok account we specify the permissions needed for the TikTok integration to be set up at Lifesight. You can confirm once you have verified the permissions setup.

![](https://files.readme.io/632ec58-image.png)

<br />

Choose the TikTok Ad account that is being connected to Lifesight for sending the Web and Offline Events.

![](https://files.readme.io/9953e97-image.png)

<br />

<br />

### Set up the Events and TikTok Pixel settings

You'll need a Pixel ID and an API Access Token from the TikTok Set up sections to set up this module. Apart from this you will need to know all events being configured during your Web SDK set up and what out of those you need to send to TikTok. Lifesight and TikTok recommend all standard events in its default configuration settings. 

1. Enter the Pixel Id and TikTok Access Token from the TikTok Set up section. 

![](https://files.readme.io/284b020-image.png)

<br />

You can generate  the Test Pixel from the TikTok section below and send Test code to test and validate events on Tiktok Events Manager.

Select the default event settings or pick and choose the events that you wish to send using TikTok Events API integration.

Once configured, TikTok will appear as active in your Integrations module.

![](https://files.readme.io/5c0211e-image.png)

<br />

<br />

## Steps to Validate Events API on TikTok and Lifesight

Test event codes are special codes you can include in your event payload to simulate events. This allows you to test your API implementation without actually recording real event data.

You can optionally enter a test event code as part of your sync configuration. Navigate to Events Manager by clicking the Assets tab, Event and then Manage Web Events. You can find your test event code in the Test Events tab. Verify that events are configured and triggered correctly through Test Events.

### Steps

1. In Events Manager, click the pixel to view its configuration details.
2. In the Test Events tab, click the test code button in Step 2 of the Test Server Events section to copy the code.
3. Follow steps from the previous section and trigger a test event.
4. Go to the Test Events tab of the pixel in Events Manager, and look for the test event in the Event Activity section. Any issues with the payload will show up to help you resolve the issues.  
   ​

   ![](https://files.readme.io/b645965-image.png)

<br />

## Events passed using the TikTok CAPI

When setting up the TikTok CAPI, Lifesight passes some events on to the channel as default data points, with an option to add more. The comprehensive list is a s below:

1. User Data
2. Search Results List View
3. Product Detail View
4. Cart View
5. Checkout Step
6. Product Add to Cart
7. Search results List View
8. Collection List View
9. Product List View Click
10. Product Add to Cart form
11. Product Removed from Cart
12. Cart reconciliation
13. Checkout Complete

<br />

> Further reading  
> If you’re looking for more information, we recommend you go through the following resources:
>
> <https://business-api.tiktok.com/portal/docs?id=1739584855420929>