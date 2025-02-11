---
title: Facebook CAPI
excerpt: >-
  Capture data & events from all web properties, & enhance ret using the
  Facebook Conversion API (CAPI).
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## What is the Facebook Conversions API?

The Facebook conversions API connects an advertiser’s marketing data (such as events on the website, app, or any business messaging tools) from various sources such as an advertiser’s server, website, mobile app, or CRM to Meta’s systems. This helps users optimize their ad targeting, decrease cost per result and measure outcomes more accurately. 

As browsers block third-party cookies, CAPI is a great solution. It allows businesses to track conversions even if users have disabled cookies, while ensuring better reliability on conversion data than cookies.

<br />

## What’s the difference between the Facebook Pixel and CAPI?

The Facebook pixel captures data & events once the pixel is placed on an advertiser’s website/app. In this case Facebook captures the events & manages data collection. The conversions API allows users to control the data being sent from their website and other properties to Facebook for optimizations, reducing noise and increasing accuracy.

<br />

## Benefits of using the Facebook CAPI

CAPI sends both front-end and back-end events, whereas with the Facebook pixel some of these events can get lost subject to browser restrictions and device changes owing to it favoring front-end events. 

With an enhanced SDK, Lifesight stores events received through the shop/site as well as through integrations (Reviews, Subscription, Wishlist, etc), for improved conversion.

Event data is enriched using the First Party ID graph and enriched data is passed back to Facebook, ensuring better scope of optimization.

<br />

## Prerequisites to setting up the Facebook CAPI

In order to set up your CAPI, you will need the following fields from your Facebook Account

Meta Pixel ID  
Your Meta pixel ID is a code snippet that tracks your website visitor activity. To locate the code:

1. Go to your Facebook Events Manager
2. Navigate to Settings
3. The field titled ‘Dataset ID’ is your Meta Pixel ID. Please copy and store it.

<br />

## Access Token

Your Meta Access Token is a string that identifies unique users, apps & pages, used to make graph API calls. To locate it:

1. Go to the Facebook Events Manager
2. Navigate to Settings
3. Scroll to the section titled ‘Conversions API’, click Generate Access Token and copy the generated Access Token.
4. Store the token for further use.

<br />

## Meta Test Code

The test code allows you to review if events are being passed from Lifesight to Facebook via the CAPI. To locate it:

1. Head to your Facebook Events Manager and go to ‘Test Events’.
2. Click on the tab titled ‘Confirm your server’s events are set up correctly’
3. Copy the test code and keep it ready for use.

<br />

## Setting up the Facebook Conversions API

1. Head to the Integrations in your left hand menu.
2. Use the native Facebook integration to connect your Facebook ad account with your Lifesight workspace. (Here’s how you can integrate Facebook)
3. Click on the integration you’ve just activated. Feed in your Facebook Pixel ID and the Access Token in the dedicated fields.
4. Optionally, to test if you’re receiving events, add the test code and click Save.
5. Once the test is successful, turn on the toggle titled ‘Go Live’ and select Save.

Your Facebook conversions API is now live and actively enriching your audience & optimizing your ad costs.

## Events passed using the Facebook CAPI

When setting up the Facebook CAPI, Lifesight passes some events on to the channel as default data points, with an option to add more. The comprehensive list is a s below:

1. View content (for products) - Default Event
2. Add to cart - Default event
3. Order placed - Default event
4. Customer created - Optional event
5. Customer updated - Optional event
6. Page viewed - Optional event

<br />

> Further reading  
> If you’re looking for more information, we recommend you go through the following resources: <https://developers.facebook.com/docs/marketing-api/conversions-api/>