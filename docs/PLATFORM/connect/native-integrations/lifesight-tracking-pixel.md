---
title: Lifesight Tracking Pixel
deprecated: false
hidden: true
metadata:
  robots: index
---
The Lifesight Tracking Pixel is a powerful JavaScript code snippet that you place on your website. Its primary function is to track website visitors and the actions they take, such as page views, sign-ups, or purchases. This data is essential for the Lifesight UMM Platform to measure campaign performance, attribute conversions, and build targetable audience segments.

<br />

## Finding Your Pixel

Before you can install the pixel, you need to retrieve your unique code snippet from the Lifesight platform.

1. Log in to your Lifesight UMM Platform account.
2. Navigate to the **Integrations** section from the main menu.
3. Click on **Custom JS**
   <br />

## Implementation Methods

<br />

You can add the Lifesight Tracking Pixel to your site in two ways: using Google Tag Manager (recommended for its ease of use) or by adding it manually to your website's source code. Select the tab below that corresponds to your preferred method.

<br />

\<Tabs>
&#x20; \<Tab title="Google Tag Manager (Recommended)">
This is the easiest and most recommended method for installing the tracking pixel.

1\. \*\*Log in\*\* to your Google Tag Manager (GTM) account.
2\. Select your website's container and go to \*\*Tags\*\* > \*\*New\*\*.
3\. Name your tag something memorable, like "Lifesight Tracking Pixel".
4\. Click on \*\*Tag Configuration\*\* and choose the \*\*Custom HTML\*\* tag type.
5\. \*\*Copy the code snippet\*\* below and paste it into the HTML field.
6\. Click on \*\*Triggering\*\* and select the \*\*All Pages\*\* trigger. This ensures the pixel loads on every page of your website.
7\. \*\*Save\*\* the tag and \*\*Publish\*\* your GTM container.
&#x20; \<br/>
&#x20; \</Tab>
&#x20; \<Tab title="Manual Setup">
&#x20;   If you don't use Google Tag Manager, you can add the pixel directly to your website's code.

\[!Warning]
We recommend having a web developer perform this task to avoid breaking your website's layout or functionality.

Copy the code snippet provided in your Setup popup window.

Access the source code of your website.

Paste the snippet just before the closing \</head> tag on every page of your website. If you use a template or a master include file for your header, you can simply place it there once.
&#x20; \</Tab>
\</Tabs>