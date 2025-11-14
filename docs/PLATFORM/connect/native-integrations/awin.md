---
title: Awin
deprecated: false
hidden: false
metadata:
  robots: index
---
Awin is a global affiliate marketing network that connects advertisers with a diverse range of publishers. Integrating Awin with Lifesight allows you to ingest performance data from your affiliate channel, enabling a complete view of its impact on your business outcomes.


### **Use Case: Modeling the Impact of the Affiliate Channel**

This integration pulls key affiliate marketing data, such as commissions, clicks, and attributed conversions, directly into Lifesight. This data is then incorporated into your Marketing Mix Models (MMM).

By doing so, you can accurately measure the affiliate channel's true contribution to sales and compare its effectiveness relative to your other marketing channels, including paid search, social media, and programmatic advertising.

### **Prerequisites: Gathering Your Awin Credentials**

Before connecting, you will need to locate two pieces of information from your Awin Advertiser account.

1. **Advertiser ID(s):** This is the unique numerical identifier for your advertiser program on the Awin platform. You can typically find this ID displayed prominently in your Awin account dashboard after logging in. If you manage multiple advertiser programs, you can connect all of them by providing each ID.

2. **API Key:** This is your authentication token that allows Lifesight to securely access your data.
   * Log in to your Awin Advertiser account.
   * Navigate to the technical settings or account profile section. This is often found under a menu item like **Account > API Credentials** or **Technical > Publisher API**.
   * In this section, you will find an option to view or generate your API access token.
   * Copy this API Key and store it in a secure location.

### **Steps to Integrate in Lifesight**

With your credentials prepared, you can now complete the connection within the Lifesight platform.

1. Navigate to the **Connect > Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**Awin**" to locate the integration tile.
3. Click on the tile. A connection modal will appear.
4. In the **Advertiser ID(s)** field, enter your Awin Advertiser ID. If you have multiple IDs, enter them separated by commas.
5. In the **API Key** field, paste the Awin API Key you retrieved.
6. Click **Connect**.