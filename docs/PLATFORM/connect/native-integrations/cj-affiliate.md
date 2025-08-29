---
title: CJ Affiliate
deprecated: false
hidden: false
metadata:
  robots: index
---
CJ Affiliate is a leading global affiliate marketing network that helps brands connect with publishers to drive growth. Integrating CJ Affiliate with Lifesight brings your partner marketing data into the platform, allowing for a complete measurement of the channel's contribution to your business goals.

<br />

### **Use Case: Incorporating Partner Marketing into the Marketing Mix**

This integration pulls key performance data from your CJ Affiliate program, such as sales, leads, and commissions, directly into Lifesight. This information is a vital input for our Marketing Mix Models (MMM).

By incorporating this data, you can conduct a direct comparison of the partner channel's Return on Investment (ROI) against all of your other marketing channels. This provides a truly holistic view of performance and helps you optimize your budget allocation.

<br />

### **Prerequisites: Gathering Your CJ Affiliate Credentials**

Before connecting, you will need to retrieve two pieces of information from your CJ Affiliate Advertiser account.

1. **Company ID(s):** This is the unique identifier for your company's advertiser program within the CJ network. You can typically find this ID in your account details or displayed in the header of the dashboard after you log in. If you manage multiple company programs, you can connect all of them.

2. **Personal Access Token:** This token serves as your secure API key for the integration.
   * Log in to your CJ Affiliate Advertiser account.
   * Navigate to the **Account** tab in the main menu.
   * Under the **Developer Center**, find and click on the **Personal Access Tokens** tab.
   * Click the **Create a new Personal Access Token** button.
   * Give the token a descriptive name, such as `Lifesight_Integration`.
   * A new token will be generated. Copy this token immediately and store it in a secure location, as it will not be shown again.

<br />

### **Steps to Integrate in Lifesight**

With your credentials ready, you can now complete the connection within the Lifesight platform.

1. Navigate to the **Connect > Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**CJ Affiliate**" to locate the integration tile.
3. Click on the tile. A connection modal will appear.
4. In the **Company IDs** field, enter your CJ Affiliate Company ID. If you have multiple IDs, enter them separated by commas.
5. In the **Personal Access Token** field, paste the token you generated from the CJ Developer Center.
6. Click **Connect**.
