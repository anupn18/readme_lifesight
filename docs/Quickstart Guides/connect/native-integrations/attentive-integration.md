---
title: Attentive
excerpt: Integrate your Attentive Account with Lifesight
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Attentive is a leading conversational commerce and mobile messaging platform specializing in SMS and MMS marketing for e-commerce and retail brands. It focuses on driving significant revenue and fostering customer loyalty by enabling brands to have personalized, two-way conversations with shoppers via text message. The platform is designed to turn subscribers into repeat, high-value customers.

### Setup Guide

1. Go to Connect > Integrations page from the navigation bar on the left.
2. Search for "Attentive" and click on the tile.

<br />

#### Create a custom app

Complete the following steps to create a custom app for your account:

1. Navigate to the [integrations setup page](https://ui.attentivemobile.com/integrations/index).
2. Click **+ Create App** in the top-right corner.
3. Enter a unique name for your app in the **App name** field.
4. Enter your email address in the **Contact email** field.This allows Attentive to contact you if there are any issues.
5. Edit the Permissions (**No Access** or **Write**) for the following APIs (by default, all APIs have **No Access** selected):
   * **Custom Attributes**—Select the permissions for the [Custom Attributes API](https://docs.attentive.com/openapi/reference/tag/Custom-Attributes/).
   * **Custom Events**—Select the permissions for the [Custom Events API](https://docs.attentive.com/openapi/reference/tag/Custom-Events/).
   * **eCommerce**—Select the permissions for the [eCommerce API](https://docs.attentive.com/openapi/reference/tag/eCommerce/).
   * **Privacy Request**—Select the permissions for the [Privacy Request API](https://docs.attentive.com/openapi/reference/tag/Privacy-Request/).
   * **Product Catalog**—Select the permissions for the [Product Catalog API](https://docs.attentive.com/openapi/reference/tag/Product-Catalog/)
   * **Subscribers**—Select the permissions for the [Subscribers API](https://docs.attentive.com/openapi/reference/tag/Subscribers/).
6. Click **Create**.The **Copy API key** modal appears.

   <Image align="center" src="https://files.readme.io/3b1c86231e0a931cf179eac2f3f91329858769110615f01156959d310e3c8039-image_2.png" />
7. Click **Copy** to copy the unique API key to your clipboard.
   * **Important!** This is the only time you will be able to copy this API key.
8. Click **X** to exit the modal after you’ve saved your API key.

<br />

#### Create a subscription webhook

Complete the following steps to create a subscription webhook:

1. Navigate to the [integrations setup page](https://ui.attentivemobile.com/integrations/index).
2. Select the custom app (in the **Built by you** section) that you previously created for the webhook.The app’s **Settings** tab appears.
3. Click the **Webhooks** tab.
4. Slide the **Event Webhook Status** toggle on to enable webhooks for your app.
5. In the **Subscribe to event notifications** section, select **Subscription webhook**.
6. Copy and save your **Signing key** to a safe location. (This is a unique key that is shared between your application and Attentive to verify the event notifications sent to your desired URLs. For more information about the signing key, see [Webhook authentication](https://docs.attentive.com/pages/webhooks/webhook-authentication/).)
7. Click **Save**.
