---
title: Identity graph
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
The Lifesight Identity Graph is a powerful tool that enables businesses to connect fragmented user data across multiple touchpoints into a single, unified customer profile. By integrating data from various online and offline sources, the Lifesight Identity Graph helps you create a comprehensive view of each individual, allowing for more personalized, data-driven marketing, and better customer experience management.

## Key Features

- Unified Customer Profiles: Consolidate data from multiple channels and platforms to create a 360-degree view of your customers.
- Cross-device Identification: Identify and track user behavior across devices (desktop, mobile, tablet, etc.), ensuring consistent and accurate attribution.
- Data Privacy & Compliance: Ensure data is handled securely and in compliance with privacy regulations such as GDPR and CCPA.
- Real-time Data Resolution: Resolve fragmented data in real-time, keeping customer profiles up to date as new data flows in.
- Scalable Data Matching: Use probabilistic and deterministic matching techniques to accurately connect data across billions of profiles, ensuring high accuracy even at scale.

## Use Cases

- Omnichannel Marketing Personalization: Leverage unified profiles to deliver personalized marketing messages across multiple channels such as email, social media, websites, and apps.
- Cross-channel Attribution: Improve attribution accuracy by linking customer interactions across touchpoints, leading to better insights into which campaigns and channels are driving results.
- Customer Journey Mapping: Track users across devices and channels to understand the full customer journey, enabling better decision-making in marketing and product development.
- Customer Retargeting: Use the Identity Graph to target users across platforms with personalized offers and ads, improving the likelihood of conversions.

## How the Identity Graph Works

1. Data Ingestion  
   Lifesight collects user data from various sources such as website visits, app usage, CRM systems, social media platforms, transaction records, and more. The data can come from both first-party and third-party sources.

2. Data Matching  
   Once the data is ingested, Lifesight uses deterministic and probabilistic data matching techniques to identify connections between different data points:
   1. Deterministic Matching: Links data using unique identifiers such as email addresses, phone numbers, or device IDs. This method ensures high accuracy in matching.
   2. Probabilistic Matching: Uses behavioral patterns, location data, and other factors to infer relationships between anonymous data points, providing insights where deterministic methods are unavailable.

3. Real-time Resolution  
   The Lifesight Identity Graph resolves customer identities in real-time. Whether a user logs into your app from a new device or makes a purchase in-store, their profile is immediately updated, ensuring you always have the most accurate data for targeting and personalization.

4. Data Privacy & Security  
   Lifesight is built with privacy in mind. All data within the Identity Graph is encrypted, and Lifesight adheres to the highest data protection standards such as GDPR, CCPA, and HIPAA, ensuring that customer information is always secure and handled in compliance with regulations.

***

The Lifesight SDK captures browser-side events such as a site-landing by a user that contains UTM tags. These users are tracked all the way through to a conversion event (registrations, form submissions, purchases, etc.). By not relying on cookie technology, the Lifesight SDK mitigates concerns related to privacy restrictions and cookie depreciation in tracking customer signals. This approach enhances the accuracy of capturing all customer touchpoints.

The Lifesight SDK gathers valuable data on website visitors and maintains a First-Party ID Graph, enabling comprehensive tracking of users from their initial interaction to a conversion event. This includes preserving information such as IP addresses, identifiers, browser fingerprints, click IDs, and other ephemeral identifiers in the browser's local storage. This approach ensures the accurate identification and retention of user information throughout their engagement with the website.