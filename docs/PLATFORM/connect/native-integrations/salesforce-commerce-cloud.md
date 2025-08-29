---
title: Salesforce Commerce Cloud
excerpt: >-
  Learn how to integrate your Salesforce Commerce Cloud store with Lifesight and
  leverage customer data for better marketing insights.
deprecated: false
hidden: true
metadata:
  robots: index
---
Salesforce Commerce Cloud (SFCC) is a leading platform for building and managing e commerce storefronts. Integrating SFCC with Lifesight allows you to pull in detailed sales, order, and customer data, which serves as the ground truth for measuring the effectiveness of your marketing efforts.

<br />

### **Use Case: Connecting Marketing Activity to Sales Performance**

This integration is fundamental for accurate Marketing Mix Modeling (MMM) and Causal Attribution. By connecting your SFCC store, you provide the essential business results that Lifesight measures against.

Lifesight uses your SFCC data, such as revenue and order volume as the primary outcome variables. This allows the platform to precisely calculate the impact of your marketing spend and activities from all other connected platforms on your actual sales performance.

### **Prerequisites: Gathering Your Salesforce Commerce Cloud Credentials**

Before connecting, you must gather five specific pieces of information from your Salesforce Commerce Cloud Business Manager and Account Manager.

#### **Part A: Finding Your Instance Details**

1. **Organization ID:** You can typically find this in the URL when you are logged into the Business Manager. It is a unique identifier for your entire organization.
2. **Short Code:** The short code is a unique identifier for your realm. It is also found in the Business Manager URL, usually a four character string that helps form the domain.
3. **Site ID:** This identifies the specific storefront you wish to connect.
   * Log in to your Salesforce Commerce Cloud Business Manager.
   * Navigate to **Administration > Sites > Manage Sites**.
   * Locate the desired site and copy its unique **Site ID**.

#### **Part B: Generating API Credentials**

You need to create a dedicated API Client to allow Lifesight to securely access your data.

1. Log in to your Salesforce Commerce Cloud **Account Manager**.
2. Navigate to the **API Client** section.
3. Click **Add API Client**.
4. Give the client a descriptive name, such as `Lifesight_Integration`.
5. Set the necessary permissions (scopes) to allow Lifesight to read sales and order data.
6. Save the new API Client configuration.
7. Upon saving, Salesforce will generate a **Client ID** and a **Client Secret**.
8. Copy both the **Client ID** and the **Client Secret** immediately and store them in a secure location. The Client Secret is only shown once.
   <br />

### **Steps to Integrate in Lifesight**

With your five credentials prepared, you can now complete the connection within the Lifesight platform.

1. Navigate to the **Connect > Integrations** tab in the Lifesight left side menu bar.
2. In the search field, type "**Salesforce Commerce Cloud**" to locate the integration tile.
3. Click on the tile. A connection modal will appear.
4. Carefully enter the **Client ID**.
5. Enter the corresponding **Client Secret**.
6. Enter your **Site ID**.
7. Enter your **Organization ID**.
8. Enter your **Short Code**.
9. Click **Validate** to finalize the integration.
