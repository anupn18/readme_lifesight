---
title: Shopify
excerpt: >-
  Learn how to integrate your Shopify store with Lifesight and leverage customer
  data for better marketing insights.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Shopify is a comprehensive e-commerce platform that provides early-stage entrepreneurs and established businesses with the tools to build, manage, and grow an online retail business. It specializes in simplifying the process of selling goods directly to consumers (D2C) by unifying all aspects of commerce—from website creation to back-office operations—into a single, user-friendly interface.

## Connect your Shopify Account

To integrate your Shopify data and allow Lifesight to collect data from your store and use it in your marketing activities:

1. Navigate to the Integrations tab in the left-hand menu bar.
2. In the search field, type "Shopify" to locate the integration.
3. Click the Shopify tile and enter your store name (the part before .myshopify.com).

   <Image align="center" src="https://files.readme.io/b09f4f7543e9563394b05cfe29c85470c11c278fea90d35e9fc4cb836dac4e12-Shopify_Install_Page.png" />
4. Click `Connect`
5. You’ll be redirected to Shopify and shown the permission screens—review and approve the installation.
6. After installation, you’ll be redirected back to Lifesight.
7. Data will begin appearing in your Dashboards, Profiles, and Segments. Full synchronization can take up to 24 hours.

You are now all set to leverage your store data and measure marketing performance based on customer behavior.

<br />

#### Additional Steps for Enabling Tracking

* Log into your Shopify store and navigate to the "Online Store" section.
* Click on "Customize Theme" to access the theme customization options.
* In the customization menu, select the "App Embeds" section on the left.
* Enable the "Lifesight SDK" and "Lifesight SDK Schema" toggles to activate Lifesight tracking.
* Click "Save" to apply your changes and successfully integrate Lifesight tracking.

<br />

### Data Collection on Lifesight

The App Embeds on the storefront capture basic events such as product_view, product_list_view and make the identify calls to identify users.

#### Events captured through Lifesight SDK

* `page_view` - Fires on any page load; captures page URL/title, referrer, UTM params, device, and session info.
* `product_view`- When a product detail page is viewed; captures product/variant IDs, handle, price, collection context, and referrer/UTMs
* `product_list_view`- When a collection/search/listing is viewed; captures list context (collection/search term), product IDs shown, positions, pagination
* `add_to_cart`- When an item is added; captures product/variant IDs, quantity, price/value, currency, and cart token
* `cart_view`- When the cart page/drawer is viewed; captures cart token, line items (IDs, qty, prices), cart value, currency
* `remove_from_cart`- When an item is removed; captures product/variant IDs removed, quantity, cart token, and updated cart value
* `thank_you_page_view`- On order status/thank-you page; captures order ID, line items, and revenue

#### Events captured through Shopify's Web Pixels

* `checkout_started` — Checkout initiated; captures checkout ID, cart token, line items, subtotal, currency, and customer/contact availability.
* `checkout_shipping_info_submitted` — Shipping method step submitted; captures checkout ID, selected shipping rate, shipping address, and updated totals.
* `payment_info_submitted` — Payment step submitted; captures checkout ID, payment gateway/type (no card PAN), billing address, and totals.
* `checkout_address_info_submitted` — Customer/address step submitted; captures checkout ID, email/phone (often hashed), shipping/billing addresses.
* `checkout_completed` — Order completed; captures order ID, checkout ID, line items, total revenue, discounts, taxes, shipping, currency, and customer ID (if logged in).
* `checkout_contact_info_submitted` — Contact step submitted; captures checkout ID, customer email/phone (often hashed), marketing opt-in, and session identifiers.

<Callout icon="❗️" theme="error">
  All checkout events are configured through Shopify's Web Pixels. Lifesight doesn't use custom JavaScript for checkout events, and we never inject code directly into checkout pages. Instead, we follow Shopify’s approved approach and use Web Pixels. All checkout events are captured through Shopify Web Pixels.
</Callout>

<br />

> 👍 In case you have any further queries, feel free to write to us at [support@lifesight.io](mailto:support@lifesight.io) and we’ll respond at the earliest.

<br />
