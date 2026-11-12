---
title: JavaScript SDK
excerpt: Integrate our Lifesight Pixel to elevate your website's tracking.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The Lifesight JS SDK, also referred to as the 'Lifesight Pixel', lets you track customer event data from your website. It is a single script, `measureinsight.min.js`, that adds a `measureinsight` object to your pages. You call `measureinsight.identify` and `measureinsight.track` to send visitor details and events to Lifesight.

Once integrated, the pixel enables Lifesight to capture valuable behavioural data from your visitors, along with a variety of URL parameters such as UTM tags, search keywords, and more.

Tracking begins even before a customer is identified, and regardless of the devices they use. Our unique algorithm merges multiple touchpoints to create a first-party identity graph, providing you with a deep understanding of their entire journey.

## What does Lifesight Pixel capture?

Lifesight Pixel tracks client-side events like a user visit or interaction with the website. These are some of the attributes that it auto-tracks:

* **UTM Parameters:** Tracks the source and journey of users as they land on your website. Every query parameter on the page address is captured, including `utm_source`, `utm_medium`, `utm_campaign`, `utm_term` and `utm_content`.
* **User Events:** Records page views on its own, and the actions you send with `identify` and `track`.
* **Marketing Identifiers:** Collects identifiers from platforms like Facebook, Google, and Snapchat, including first-party cookies and click IDs. From the page address it reads the click IDs `fbclid`, `gclid`, `msclkid`, `ttclid`, `ScCid`, `gbraid`, `wbraid`, `rdt_cid` and `li_fat_id`. From the browser it reads the cookies `_fbp`, `_fbc`, `_gid`, `_ttp`, `_scid` and `_rdt_uuid`.
* **Visitor and Session IDs:** Gives each browser an anonymous visitor ID that lasts 2 years, and each visit a session ID that lasts 24 hours. Both are kept in first-party cookies and local storage.

## Events tracked automatically

The SDK sends these events on its own as soon as it loads. You don't need to set up anything for them.

| Event | When it is sent |
| :-- | :-- |
| `page_view` | On every page load, and on route changes in single-page apps that use `history.pushState` |
| `identify` | At the start of each visit, with the visitor's IDs and any details saved from an earlier identify call |

Every event carries these properties, including the events you send with `identify` and `track`:

| Property | What it holds |
| :-- | :-- |
| `identifiers.anonymous_id` | The anonymous visitor ID |
| `session_id` | The visit (session) ID |
| `message_id` | A unique ID for the event |
| `event_name` | The event, for example `page_view` |
| `event_timestamp` | When the event happened, in ISO 8601 format |
| `shop` | Your website domain (see [Before you start](#before-you-start)) |
| `source` | Always `web` |
| `context.page_url` | The full page address |
| `context.page_path` | The page path, for example `/products/blue-shirt` |
| `context.page_title` | The page title |
| `context.page_search` | The query string of the page address |
| `context.page_referrer` | The page the visitor came from |
| `context.ip` | The visitor's public IP address, looked up once per browser session |
| `context.locale` | The browser language, for example `en-US` |
| `context.user_agent` | The browser's user agent |
| `queries.utm_source`, `queries.utm_medium`, ... | One entry for each query parameter on the page address |
| `ephemeral_identifiers.gclid`, `ephemeral_identifiers.fbp`, ... | The click IDs and ad cookies listed above, with any leading underscore removed |
| `identifiers.email`, `identifiers.phone`, `identifiers.customer_id` | Saved from the visitor's last identify call, and empty until then |
| `customer_name`, `customer_first_name`, `customer_last_name` | Saved from the visitor's last identify call, and empty until then |

## Before you start

* **A Google Tag Manager container on your website**, if you use Method 1. If you don't have one yet, follow Google's [setup and installation guide](https://support.google.com/tagmanager/answer/14842164).
* **Your website domain as Lifesight knows it.** Every event carries your website domain as `shop`, and Lifesight uses it to match events to your workspace. By default the SDK takes the page's address, keeps `www.` and drops any other subdomain: `https://www.example.com` is sent as it is, and `https://shop.example.com` is sent as `https://example.com`. If the domain set up in your Lifesight workspace is different, set it in the base tag (Step 1). Ask your Lifesight contact if you're not sure.

# Method 1: Set up with Google Tag Manager [Recommended]

You add one base tag that loads the SDK on every page, then one tag for each event you want to send.

## Step 1: Add the Lifesight base tag

1. In your GTM container, go to **Tags** and click **New**.
2. Name the tag `LS - Base Tag`, click **Tag Configuration** and choose **Custom HTML**.
3. Paste this code:

```html
<script>
  (function () {
    // Leave empty unless your Lifesight website domain differs from this site's
    // main domain, for example "https://www.example.com".
    var LIFESIGHT_DOMAIN = "";

    var queue = (window.measureinsightQueue = window.measureinsightQueue || []);

    function sdkReady() {
      var mi = window.measureinsight;
      return !!(mi && mi.track && mi.getVisitorId && mi.getVisitorId());
    }

    function flush() {
      if (!sdkReady()) return;
      while (queue.length) {
        try {
          queue.shift()(window.measureinsight);
        } catch (e) {
          console.error(e);
        }
      }
    }

    window.measureinsightReady =
      window.measureinsightReady ||
      function (callback) {
        queue.push(callback);
        flush();
      };

    if (document.getElementById("measureinsight-sdk")) return;
    var script = document.createElement("script");
    script.id = "measureinsight-sdk";
    script.src = "https://storage.googleapis.com/measure-insight/measureinsight.min.js";
    script.onload = function () {
      if (LIFESIGHT_DOMAIN) {
        window.measureinsight.configure({ domain: LIFESIGHT_DOMAIN });
      }
      var tries = 0;
      (function waitForVisitorId() {
        if (sdkReady()) return flush();
        if (++tries < 200) setTimeout(waitForVisitorId, 50);
      })();
    };
    document.head.appendChild(script);
  })();
</script>
```

4. Under **Triggering**, choose **Initialization - All Pages**.
5. Open **Advanced Settings** › **Tag firing options** and choose **Once per page**.
6. Click **Save**.

The code loads the SDK once and defines `measureinsightReady`, which every other Lifesight tag uses. An event that fires before the SDK is ready waits in a queue, and is sent as soon as the SDK has set up the visitor ID. A purchase pushed while the order confirmation page is still loading is a common example. Called directly at that moment, `measureinsight` doesn't exist yet and the event is lost.

The **Initialization - All Pages** trigger fires before any other tag on the page, so `measureinsightReady` exists before your event tags run.

<Image align="center" border={true} alt="LS - Base Tag in Google Tag Manager, a Custom HTML tag with the Lifesight loader code and the Initialization - All Pages trigger" src="https://files.readme.io/2ad0d73fbc39ee95ef7f9aec640a8c005e7c902541c8f76c8175450dc4d2c50d-01-gtm-base-tag.png" />

> 📘 Cookie consent
>
> If your site must have consent before tracking, add the same requirement to every Lifesight tag: open **Advanced Settings** › **Consent Settings**, choose **Require additional consent for tag to fire** and add the consent types your policy needs, for example `analytics_storage`.

## Step 2: Create variables for the values you send

Each value you send to Lifesight comes from a GTM variable. Create them under **Variables** › **User-Defined Variables** › **New**.

* **Values in the dataLayer:** use a **Data Layer Variable** and keep **Data Layer Version** at **Version 2**. Write the key with dots, and write array positions as numbers. For example, the first product's ID in a GA4 `view_item` push is `ecommerce.items.0.item_id`, not `ecommerce.items[0].item_id`. Leave out the push's position in the dataLayer: GTM merges every push and reads keys by name.
* **Values in a form:** use a **DOM Element** variable. Set **Selection Method** to **CSS Selector**, **Element Selector** to the field's selector, for example `#signup-form [name='email']`, and **Attribute Name** to `value`. It returns what the visitor typed.
* **Page details:** GTM's built-in variables, such as **Page URL**, are ready to use.

To see what a Data Layer Variable will read, open your site and run this in the browser console, with your container ID:

```javascript
google_tag_manager["GTM-XXXXXXX"].dataLayer.get("ecommerce.items.0.item_id")
```

<Image align="center" border={true} alt="A Data Layer Variable in Google Tag Manager reading ecommerce.items.0.item_id" src="https://files.readme.io/f5ecb14e0e5c0430c84bb95d2144eb4fe67aec1d71d0922003e82948db45f9ad-02-gtm-data-layer-variable.png" />

## Step 3: Create a trigger for each event

Create triggers under **Triggers** › **New**.

* **Events pushed to the dataLayer:** use a **Custom Event** trigger, with **Event name** exactly as your site pushes it, for example `view_item` or `purchase`.
* **Form submissions:** use a **Form Submission** trigger. Choose **Some Forms**, then set **Form Element** **matches CSS selector** to your form's selector, for example `#signup-form`.

<Image align="center" border={true} alt="A Custom Event trigger in Google Tag Manager for the view_item event" src="https://files.readme.io/0ce20a6a1b2e00e1546767e985eec5c2c151f5cfc491af037663961165ef8a78-03-gtm-custom-event-trigger.png" />

## Step 4: Identify visitors

Add an identify tag for each place a visitor signs up, logs in or submits a form with their details.

1. Create a **Custom HTML** tag, for example `LS - Identify - Signup form`, with this code. Replace the variable names with your own:

```html
<script>
  measureinsightReady(function (mi) {
    mi.identify({
      identifiers: {
        email: {{Signup form - email}},
        phone: {{Signup form - phone}}
      },
      customer_first_name: {{Signup form - first name}},
      customer_last_name: {{Signup form - last name}}
    });
  });
</script>
```

2. Under **Triggering**, choose the form's trigger from Step 3.

Keep in mind:

* **Put variables outside quotes.** GTM then inserts each value as a proper JavaScript value. Inside quotes every value becomes text, so prices and quantities arrive as text, and an apostrophe in a name can break the code.
* **Send at least one of `customer_id`, `email` or `phone`** in `identifiers`. Use `customer_id` only for your own customer ID, never for an email address.
* **Identify once per action.** The SDK saves these details in the browser and adds them to every later event, including events on the next pages.

<Image align="center" border={true} alt="The LS - Identify - Signup form Custom HTML tag calling mi.identify inside measureinsightReady" src="https://files.readme.io/bfb01b6a0e493e4ccad0cfd12223fbc239bc6c5eeaa4b9b1d517434d6b30b175-04-gtm-identify-tag.png" />

## Step 5: Track events

Add one **Custom HTML** tag for each event, with that event's trigger from Step 3. Use the standard event names in the table below. For example, a product view:

```html
<script>
  measureinsightReady(function (mi) {
    mi.track("product_view", {
      product: {
        product_id: {{DLV - ecommerce.items.0.item_id}},
        product_name: {{DLV - ecommerce.items.0.item_name}},
        lineitem_price: {{DLV - ecommerce.items.0.price}},
        product_url: {{Page URL}}
      }
    });
  });
</script>
```

Don't add an `identifiers` object to a track call. It replaces the visitor ID the SDK adds, and the SDK then drops the event. Call identify instead (Step 4).

<Image align="center" border={true} alt="The LS - Track - product_view Custom HTML tag calling mi.track inside measureinsightReady" src="https://files.readme.io/a1a2a24e9c61767189c7ea8cd20707bbeeb7975cecb3a7d711473d17a88e8bd7-05-gtm-track-tag.png" />

### Examples of standard e-commerce client-side events that you can set up on your tag manager

| Event Name          | Name                  | Name                  | Description                                                                                        |
| ------------------- | --------------------- | --------------------- | -------------------------------------------------------------------------------------------------- |
| product_view        | Viewed Product        | Product Viewed        | When a Product is viewed.                                                                          |
| product_search      | Search                | Search                | When a search is performed.                                                                        |
| add_to_cart         | Added to Cart         | Added to Cart         | When an item is added to the shopping cart.                                                        |
| product_list_view   | Viewed Product List   | Product List Viewed   | When list of products on page, cart or order is viewed.                                            |
| checkouts_create    | Created Checkout      | Checkout Created      | When the checkout process is started.                                                              |
| checkouts_update    | Updated Checkout      | Checkout Updated      | When the checked list is updated with new set of items.                                            |
| abandoned_checkout  | Abandoned Checkout    | Checkout Abandoned    | When payment information is added in the checkout flow.                                            |
| orders_paid         | Paid for Order        | Payment Completed     | When a payment is completed.                                                                       |
| orders_create       | Placed Order          | Order Placed          | When an order is placed.                                                                           |
| form_submit         | Submitted Form        | Form Submitted        | When a form is submitted for newsletter subscription or zero party survey data form fill.          |
| thank_you_page_view | Viewed Thank You Page | Thank You Page Viewed | The Thank you Page viewed by the user right when the order is completed after the payment is done. |

While configuring the events, make sure you use the same event naming convention mentioned in the above table. In a tag, the call looks like `mi.track("add_to_cart", { ... })` inside `measureinsightReady`. The [SDK reference](#sdk-reference) below has example properties.

## Step 6: Test in Preview mode

1. Click **Preview**, enter your website address and click **Connect**. Your site opens with Tag Assistant attached.
2. In Tag Assistant, check that `LS - Base Tag` fired on **Initialization**, and that each event tag fired on its trigger.
3. On your site, open the browser's developer tools:
   * In the **Console**, run `measureinsight.debug()` and reload the page. The SDK now prints every event it sends. Run `measureinsight.debug(false)` to stop.
   * In the **Network** tab, filter by `gateway.dev`. Each event is a POST request, and its **Payload** shows `event_name` and the properties.

Events you send in Preview mode reach your live Lifesight workspace.

## Step 7: Publish

Click **Submit**, add a version name and click **Publish**.

> 👍 That's it! You have now added Lifesight Pixel to your website.
>
> You can now see whether the system events, such as page view, are flowing in by going back to your Lifesight Workspace and by looking at customer Profiles.

## Single-page applications

The SDK sends `page_view` on its own when your app changes the route with `history.pushState`. Back and forward navigation isn't tracked on its own. To track it, add a **Custom HTML** tag with a **History Change** trigger:

```html
<script>
  measureinsightReady(function (mi) {
    mi.pageView();
  });
</script>
```

The SDK skips a page view for the path it has just tracked, so routes changed with `history.pushState` aren't counted twice.

# SDK reference

## Identify

The identify API lets you identify a user and associate them to their actions. It also lets you record any traits about them like their name, email, etc. Once you make the identify call, the SDK persists the user information and passes it to the subsequent calls.

```javascript
measureinsight.identify(traits)
```

`traits` is an object with the visitor's identifiers and details. Pass at least one of `customer_id`, `email` or `phone` in `identifiers`. These are the traits you can send; dates use the `yyyy-mm-dd` format:

```json
{
  "identifiers": {
    "customer_id": "12314",
    "email": "jane@example.com",
    "phone": "+14155550123"
  },
  "customer_name": "Jane Doe",
  "customer_first_name": "Jane",
  "customer_last_name": "Doe",
  "address": {
    "street": "High Street",
    "city": "Bengaluru",
    "state": "Karnataka",
    "postal_code": "560067",
    "country": "India"
  },
  "age": "23",
  "birthday": "2002-11-22",
  "gender": "Female",
  "title": "Product Manager",
  "username": "janedoe",
  "description": "Prefers email",
  "website": "www.example.com",
  "avatar": "https://www.example.com/avatar.png",
  "company": {
    "id": "1234",
    "name": "Example Inc",
    "industry": "Ad-Tech",
    "employee_count": "200",
    "plan": "Platinum"
  },
  "customer_created_at": "2024-03-13T10:23:19.713Z",
  "customer_updated_at": "2024-03-13T10:25:19.713Z",
  "customer_orders_count": "42",
  "customer_revenue": "420000",
  "customer_last_order_name": "#1042",
  "customer_tags": "Highvaluecustomer",
  "default_city": "Culiacan",
  "default_zip": "482001",
  "default_country_name": "Mexico",
  "email_marketing_consent": "false",
  "sms_marketing_consent_state": "false",
  "whatsapp_marketing_consent": "true"
}
```

### When should I call Identify?

Ideally, you should call the `identify` method in the following scenarios:

* After a user registers on your website or app
* After a user logs in to your site or app
* When a user submits a form
* When a user updates their information, e.g., residential address, email ID
* When you load a page accessible by a logged-in user: Although this is optional, many tools (such as Intercom, for example) require an initial identify call to know who the user is when they first start the session.

_Note: You don't need to use the 'identify' function for anonymous visitors. Lifesight already assigns them an anonymous ID, so page views and 'track' calls are enough._

## Track

Track call allows you to record any actions your users perform, along with any properties that describe the action.

```javascript
measureinsight.track(eventName, properties)
```

| Parameter | Description |
| :-- | :-- |
| `eventName` | The name of the event, from the standard event names, for example `product_view` or `add_to_cart` |
| `properties` | The event's properties. If there are none, pass an empty object (`{}`) |

**Example: `product_view`**

```javascript
measureinsight.track("product_view", {
  product: {
    product_id: 6814932369498,
    product_name: "Halloween Printed Dog Collar",
    product_url: "/products/bootique-hw-collar",
    product_image_url: "https://cdn.example.com/products/collar.png",
    lineitem_price: 4.99,
    sku: "ABC123"
  }
});
```

**Example: `form_submit`**

```javascript
measureinsight.track("form_submit", {
  campaign_name: "Newsletter", // one campaign can have several forms
  form_name: "newsletter_signup",
  cta: "register", // the call to action
  input: {
    email: "jane@example.com",
    phone: "+14155550123",
    first_name: "Jane",
    last_name: "Doe",
    birthday: "1999-10-18", // yyyy-mm-dd
    address: {
      street: "High Street",
      city: "Bengaluru",
      state: "Karnataka",
      postal_code: "560067",
      country: "India"
    },
    company: {
      name: "Example Inc",
      industry: "Ad-Tech",
      employee_count: "200"
    },
    website: "www.example.com",
    website_platform: "shopify",
    product_interested: "connect",
    monthly_ad_spent: "",
    additional_information: ""
  }
});
```

**Example: `orders_create`**

```javascript
measureinsight.track("orders_create", {
  data: {
    id: "1042",
    name: "#1042",
    total_price: 129.0,
    total_tax: 9.0,
    currency: "USD",
    line_items: [
      {
        product_id: 6814932369498,
        sku: "ABC123",
        title: "Halloween Printed Dog Collar",
        price: 60.0,
        quantity: 2
      }
    ],
    discount_codes: [{ code: "WELCOME10", amount: 6.0, type: "percentage" }]
  }
});
```

# Method 2: Add the SDK to your website code

Use this method when you can't use Google Tag Manager, or when your developers prefer to send events from your site's own code.

## Step 1: Add the base snippet to every page

Paste this snippet into the `<head>` of every page, for example in your site's main layout or theme template. It is the same code as the GTM base tag: it loads the SDK once and defines `measureinsightReady`.

```html
<script>
  (function () {
    // Leave empty unless your Lifesight website domain differs from this site's
    // main domain, for example "https://www.example.com".
    var LIFESIGHT_DOMAIN = "";

    var queue = (window.measureinsightQueue = window.measureinsightQueue || []);

    function sdkReady() {
      var mi = window.measureinsight;
      return !!(mi && mi.track && mi.getVisitorId && mi.getVisitorId());
    }

    function flush() {
      if (!sdkReady()) return;
      while (queue.length) {
        try {
          queue.shift()(window.measureinsight);
        } catch (e) {
          console.error(e);
        }
      }
    }

    window.measureinsightReady =
      window.measureinsightReady ||
      function (callback) {
        queue.push(callback);
        flush();
      };

    if (document.getElementById("measureinsight-sdk")) return;
    var script = document.createElement("script");
    script.id = "measureinsight-sdk";
    script.src = "https://storage.googleapis.com/measure-insight/measureinsight.min.js";
    script.onload = function () {
      if (LIFESIGHT_DOMAIN) {
        window.measureinsight.configure({ domain: LIFESIGHT_DOMAIN });
      }
      var tries = 0;
      (function waitForVisitorId() {
        if (sdkReady()) return flush();
        if (++tries < 200) setTimeout(waitForVisitorId, 50);
      })();
    };
    document.head.appendChild(script);
  })();
</script>
```

Set `LIFESIGHT_DOMAIN` only when your Lifesight website domain differs from your site's main domain (see [Before you start](#before-you-start)). If your site must have consent before tracking, add the snippet only after the visitor agrees.

## Step 2: Identify visitors

Call identify after a sign-up, a login or a form submit:

```javascript
measureinsightReady(function (mi) {
  mi.identify({
    identifiers: {
      customer_id: user.id,
      email: user.email,
      phone: user.phone
    },
    customer_first_name: user.firstName,
    customer_last_name: user.lastName
  });
});
```

## Step 3: Track events

Wrap every call in `measureinsightReady`, so an event sent before the SDK has loaded isn't lost:

```javascript
measureinsightReady(function (mi) {
  mi.track("orders_create", {
    data: {
      id: order.id,
      name: order.number,
      total_price: order.total,
      total_tax: order.tax,
      currency: order.currency,
      line_items: order.items.map(function (item) {
        return {
          product_id: item.productId,
          sku: item.sku,
          title: item.name,
          price: item.price,
          quantity: item.quantity
        };
      })
    }
  });
});
```

Use the event names and properties from the [SDK reference](#sdk-reference). As in GTM, don't add an `identifiers` object to a track call.

## Step 4: Single-page applications

Add the snippet once, in the layout that wraps every route. The SDK sends `page_view` on its own for route changes made with `history.pushState`. To also track back and forward navigation, call `pageView` from your router's route-change hook. The SDK skips a repeat of the path it has just tracked, so nothing is counted twice:

```javascript
measureinsightReady(function (mi) {
  mi.pageView();
});
```

## Step 5: Allow the SDK in your Content Security Policy

If your site sends a Content-Security-Policy header, allow these addresses:

| Directive | Address | Used for |
| :-- | :-- | :-- |
| `script-src` | `https://storage.googleapis.com` | Loading the SDK |
| `frame-src` | `https://storage.googleapis.com` | A hidden frame the SDK uses for storage |
| `connect-src` | `https://moda-cdp-message-prd-7jirubb0.uc.gateway.dev` | Sending events to Lifesight |
| `connect-src` | `https://api.ipify.org` | Looking up the visitor's IP address |

## Step 6: Check that it works

Open your site and the browser's developer tools:

* **Console:** `typeof measureinsight` returns `"object"`, and `measureinsight.getVisitorId()` returns the visitor ID. Run `measureinsight.debug()` and reload to print every event the SDK sends.
* **Network:** filter by `gateway.dev`. Each event is a POST request, and its **Payload** shows `event_name` and the properties.
* **Application** › **Cookies:** look for `measureinsight_visitor` and `measureinsight_visit`.
