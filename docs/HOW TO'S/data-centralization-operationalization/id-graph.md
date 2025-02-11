---
title: How we persist customer identity
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Introduction

Lifesight utilizes a sophisticated first-party identity graph to gather and organize profile attributes. This comprehensive document outlines the process of collecting information through the Lifesight SDK (pixel) deployed on client websites. It also explains how the pixel, which is independent of first-party cookies, utilizes browser local storage to store user identifiers.

## Lifesight SDK Deployment

The Lifesight SDK, also known as the Lifesight pixel, is a powerful tool for collecting user data on client websites. This pixel is deployed on the client website and is responsible for capturing various attributes related to user profiles. The pixel is also responsible for collecting essential events that occur on the website. Events and their properties are captured through the pixel and are used to build the customer journeys that could potentially lead to conversions.

To understand how Lifesight SDK works, please refer to the following documents:

1. Manual Set-Up: [Lifesight Manual Setup](https://dash.readme.com/project/lifesight/v1.0/docs/lifesight-pixel-js-sdk-1)
2. GTM Container Based Setup: [GTM Based Setup](https://dash.readme.com/project/lifesight/v1.0/docs/lifesight-pixel-gtm-container)

## First-Party Identity Graph

Lifesight's first-party identity graph is the backbone of its data collection process. This graph allows Lifesight to capture and organize profile attributes in a meaningful way. By leveraging first-party data, Lifesight ensures that the information collected is accurate and reliable.

Data Captured by Lifesight

* IP Address
* User Agent
* Ephemeral Identifiers such as click IDs
* Email
* Phone

Data Assigned by Lifesight

* Anonymous ID (unique Lifesight ID for each anonymous profile)
* Profile ID
* Session ID (unique Lifesight ID for each user session)

## Agnostic of First Party Cookies

One key feature of the Lifesight pixel is that it is agnostic of first-party cookies. This means that Lifesight does not rely on cookies to track user behavior or gather profile attributes. Instead, the pixel utilizes browser local storage to store user identifiers. This approach ensures that Lifesight can collect and store data in a privacy-friendly manner.

## Utilizing Browser Local Storage

Browser local storage is a secure and efficient way to store data on a user's device. Lifesight uses browser local storage to store user identifiers, which are then used to link profile attributes to specific users. By using local storage, Lifesight ensures that user data is stored securely and can be accessed quickly when needed.

## Conclusion

The Lifesight SDK, with its robust first-party identity graph and reliance on browser local storage, is a powerful tool for collecting and organizing profile attributes and website events. By deploying the Lifesight pixel on their websites, clients can gather valuable insights into user behavior and demographics, all while ensuring data privacy and security.
