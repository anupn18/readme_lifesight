---
title: How to install Javascript SDK
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
Lifesight’s Custom Web SDK and Custom web hook integrations helps capture the **identifiers** and **events** performed by anonymous and logged in users from the client and the server side. Below are the steps involved in configuring both at your end.

***

### **Web - Client Side Implementation of Lifesight Pixel**

**How does the Lifesight Pixel work and what does Lifesight capture?**

The website operator must add the tracking pixel to the website’s HTML code or use a tag manager such as Google Tag Manager. 

*Note : The below document assumes the use of Google Tag Manager to set up the client side SDK.*

If a user visits the website and performs actions on the website, the SDK captures these as client side events based on the tags, triggers and variables configured in the Google tag manager tag implementation.  These are some of the attributes that we auto track.

* identifiers : Lifesight assigns anonymous\_id (also persisted in the browser’s local storage) to every visitor
* page\_view : Lifesight auto tracks every Page Views along with meta information about the page
* marketing identifiers : Lifesight captures facebook , google, snap identifiers - their first party cookies and click IDs

**Step 1 :  Set up the Custom JS SDK as a Custom HTML Tag on Google Tag Manager**

In your Google Tag Manager , please place the below script as Custom HTML tag. This JS SDK ( hosted and configured with a server at [sdk.lifesight.io](http://sdk.lifesight.io)) and it automatically tracks all anonymous page views of your website visitors.

```jsx
<script src="https://sdk.lifesight.io/lifesight.min.js"></script>

```

<br />

<br />

*Note - This trigger (Page View - Window Loaded) is for a SPA websites ( React JS / Next JS based Websites). For regular websites, Page View trigger will suffice*

**Step 2 :** For every event that you wish to pass to Lifesight (besides page*view which is auto-tracked), you need to create the required variables, triggers and tags that need to be configured for sending the data through our Identify and Track calls.\
\_Note : You do not need to configure page views as the data for page view is auto tracked and sent.*

For example :\
**Data Layer Variables** that are configured using the form elements in the website code. 

<br />

**Triggers** that determine when the event should be initiated and on what action by the user: 

<br />

**Tags : Identify** pixel tag calls that pass the the required Identifier values from the data variables on trigger of an event like form submit. 

<br />

**Tags : Track** pixel tag calls that pass the  required identifier and event values ( event name and event properties) from the data variables on trigger of an event like form submit. 

<br />

## **Examples of standard E-commerce Client side events that you can set up on your Tag Manager are :**

| **Lifesight Pixel Event Name** | **Lifesight** **Display Name** | **Customer’s Event Name** | **Description**                                                                                    |
| ------------------------------ | ------------------------------ | ------------------------- | -------------------------------------------------------------------------------------------------- |
| product\_view                  | Viewed Product                 | Product Viewed            | When a Product is viewed.                                                                          |
| add\_to\_cart                  | Added to Cart                  | Added to Cart             | When an item is added to the shopping cart.                                                        |
| checkouts\_create              | Created Checkout               | Checkout Created          | When the checkout process is started.                                                              |
| form\_submit                   | Submitted Form                 | Form Submitted            | When a form is submitted for newsletter subscription or zero party survey data form fill.          |
| thank\_you\_page\_view         | Viewed Thank You Page          | Thank You Page Viewed     | The Thank you Page viewed by the user right when the order is completed after the payment is done. |

*Note : If you wish to track more events, get in touch with our product specialist to set it up for you*

While configuring the events, make sure you use the same event naming convention mentioned in the above table. Some examples given below in detail.\
For example : If you want to track add to carts, the way to call the tag in the Google Tag manager is lifesight.track ( "add\_to\_cart", \{identifiers…}) 

**Examples of Identify Calls** 

1. Identify Function

Inputs for Identify Call that needs to be configured in GTM 

```jsx
Below are all possible traits users can use 
(at least one identifier must be passsed - customer_id, email, phone i)

{
    "identifiers":
    {
    "customer_id": "123",
    "email": "rohit.sai@lifesight.io",
    "phone": "1234567899"
    }
    "customer_name": "", 
    "customer_first_name": "",
    "customer_last_name": "",
    "address":
    {
        "city": "Bengaluru",
        "country": "India",
        "postalCode": "560067",
        "state": "Karnataka",
        "street": "High Street"
    },
    "age": "23",
    "birthday": "2002-11-22",  //format is fixed to be yyyy-mm-dd
    "company":
    {
        "name": "Lifesight",
        "id": "1234",
        "industry": "Ad-Tech",
        "employee_count": "200",
        "plan": "Platinum"
    },
    "description": "Tall",
    "gender": "Male",
    "title": "Product Intern",
    "username": "RishiZen",
    "website": "www.rishi.com",
    "Avatar": "www.pathToImage.com"
    
}

sample function call: (This is what user configures in GTM for the Identify call 
on any event trigger)

lifesight.identify({
"identifiers":
    {
    "customer_id": "123",
    "email": "rohit.sai@lifesight.io",
    "phone": "1234567899"
    },
    "customer_name": "rohit sai",
    "customer_first_name": "rohit",
    "customer_last_name": "sai"
})
```

**Example of how this Identify call is configured on Google Tag Manager** 

![Screenshot 2023-10-17 at 8.14.31 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4007e2ae-19ec-4b65-bde1-bde98f77fbb3/37af412c-9a43-4c31-a011-e77d45ec47c7/Screenshot_2023-10-17_at_8.14.31_PM.png)

```jsx

sample function call:
lifesight.track('product_list_view'); //
```

Example of **product\_view payload - Track call** 

Payload: 

```jsx
**user input**: properties the user can configure for product related information
{
        "lineitem_price": 84.99,
        "product_id": 6814932172890,
        "product_image_url": "//cdn.shopify.com/s/files/1/0572/8498/4922/products/Product1.png?v=1667508010",
        "product_name": "Pupman Complete Essentials Chicken & Rice Dry Food: New Born Puppy",
        "product_url": "/products/royalcanin-labret-adultdog",
        "sku": "RC-BHN-AD-18LB"
 }

sample function call:

lifesight.track 
  ( "product_view",  
   {
    "product":
     {
        "lineitem_price": 4.99,
        "product_id": 6814932369498,
        "product_image_url": "//cdn.shopify.com/s/files/1/0572/8498/4922/products/Product8.png?v=1667508518",
        "product_name": "Pupman Bootique Halloween Printed Dog Collar",
        "product_url": "/products/bootique-hw-collar",
        "sku": "ABC123"
    }
 }
)
```

Note: Additional fields if needed can be configured added upon request of the client

**Example of how this Track call is configured on Google Tag Manager** 

![Screenshot 2023-10-17 at 8.15.37 PM.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/4007e2ae-19ec-4b65-bde1-bde98f77fbb3/b36e9c4f-0786-4bc9-997a-12616353069b/Screenshot_2023-10-17_at_8.15.37_PM.png)

Example of **add\_to\_cart event payload - Track call**

```jsx
lifesight.track ( "add_to_cart",
    {
    "product":
     {
        "lineitem_price": 7.99,
        "product_id": 6814932369498,
        "product_image_url": "//cdn.shopify.com/s/files/1/0572/8498/4922/products/Product8.png?v=1667508518",
        "product_name": "Pupman Bootique Halloween Printed Dog Collar",
        "product_url": "/products/bootique-hw-collar",
        "sku": "Bootique-HW-Collar-L"
    }
 }
)
```

Example of **cart\_view event payload - Track call**

```jsx
lifesight.track('**cart_view**', {
"cart":
    [
        {
            "cart_url": "https://pupman.shop/cart",
            "current_subtotal": 30,
            "lineitem_price": 30,
            "product_id": 8133156077863,
            "product_image_url": "https://cdn.shopify.com/s/files/1/0572/8498/4922/products/cotton-tote-bag-black-front-63f205ce6075f.jpg?v=1676805599",
            "product_name": "Pupman Cotton tote bag",
            "product_url": "/products/pupman-cotton-tote-bag?variant=44475112718631",
            "quantity": 1,
            "sku": "9992372_16287"
        },
        {
            "cart_url": "https://pupman.shop/cart",
            "current_subtotal": 84.99,
            "lineitem_price": 84.99,
            "product_id": 6814932172890,
            "product_image_url": "https://cdn.shopify.com/s/files/1/0572/8498/4922/products/Product1.png?v=1667508010",
            "product_name": "Pupman Complete Essentials Chicken & Rice Dry Food: New Born Puppy",
            "product_url": "/products/royalcanin-labret-adultdog?variant=43707797995815",
            "quantity": 1,
            "sku": "RC-BHN-AD-18LB"
        }
    ]
 });

```

Example of **thank\_you\_page\_view event payload - Track call**

```jsx
lifesight.track("thank_you_page_view")
```

Example of **Form Submit Event Payload - Track Call** 

```jsx
lifesight.track ("form_submit",
     {
    "campaign_name": "List_test", // there can be multiple forms under this campagin name
    "form_name": "List_test",   // Sign Up Newsletter form
    "cta": "register",  //Call to Action 
    "identifiers":
    {
        "anonymous_id": "4c01a409-b70a-49a3-aa40-ac5975ec8087",
        "email": "rohit.sai@getmoda.io"
    },
    "input":
    {
        "email": "rohit.sai@lifesight.io",
        "phone": "+91xxxxxxxxxx",
        "birthday": "1999-10-18",   //format is fixed to be yyyy-mm-dd
        "last_name": "sai",
        "first_name": "rohit",
        "address":
        {
        "city": "Bengaluru",
        "country": "India",
        "postal_code": "560067",
        "state": "Karnataka",
        "street": "High Street"
        },
        "age": "23",
        "company":
        {
            "name": "Lifesight",
            "id": "1234",
            "industry": "Ad-Tech",
            "employee_count": "200",
            "plan": "Platinum"
        },
        "description": "Tall",  
        "gender": "Male",
        "title": "Product Intern",
        "website": "www.rishi.com",
        "website_platform":"shopify",  
        "Product_interested":"connect", 
        "contacts_count":"",
        "monthy_ad_spent": "",
        "additional_information":""
    }
  }
)
```
