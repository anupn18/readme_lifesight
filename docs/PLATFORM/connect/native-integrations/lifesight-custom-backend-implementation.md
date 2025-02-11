---
title: Lifesight Custom Backend Implementation
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
**How does the Server Side events tracking work and what does Lifesight capture?**

The data operator/admin needs to send the server-side events to a custom webhook endpoint, configured specially to receive server-side events grouped under Orders, Checkouts and Customers. Details on how this needs to be implemented is explained below.

## API Requests

A POST request would need to be made to Lifesight’s endpoint with JSON data sent in the payload.

### Endpoint

```java
POST https://moda-transform-webhook-data-prd-7jirubb0.uc.gateway.dev/transform-webhook-data?key={{API_Key}}&workspace={{workspace}}&source={{source_name}}&event_name={{event_name}}
```

### Query Parameters

[block:parameters]
{
  "data": {
    "h-0": "Key",
    "h-1": "Value",
    "0-0": "key",
    "0-1": "API Key for Lifesight’s endpoint - Will be shared when implementation begins",
    "1-0": "workspace",
    "1-1": "Workspace name for the account created for you on Lifesight",
    "2-0": "source",
    "2-1": "Source of data - Will be shared when implementation begins",
    "3-0": "event_name",
    "3-1": "POSSIBLE VALUES:  \norders_create, orders_updated, orders_fulfilled, orders_partially_fulfilled, orders_paid, orders_cancelled, checkouts_create, checkouts_update, customers_create, customers_update"
  },
  "cols": 2,
  "rows": 4,
  "align": [
    null,
    null
  ]
}
[/block]


## Orders

All order events would have the same payload structure. These events include `orders_create`, `orders_updated`, `orders_fulfilled`, `orders_partially_fulfilled`, `orders_cancelled`. The event to be sent is to be specified in the `event_name` query parameter in the API request.

### Mandatory and Suggested Fields in the Orders Payload

| Field                                                                                   | Data Type                                                              | Mandatory/Suggested                                  | Sample Value                                      | Description                                                                                                                                                                                                                          |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                                                                                      | Integer                                                                | Mandatory                                            | 5766207635528                                     | ID of the Order                                                                                                                                                                                                                      |
| checkout_id                                                                             | Integer                                                                | Suggested                                            | 40082301255752                                    | ID of the checkout that led to the order                                                                                                                                                                                             |
| contact_email                                                                           | String                                                                 | Suggested                                            | [jeevan@lifesight.io](mailto:jeevan@lifesight.io) | Contact email of the customer placing the order                                                                                                                                                                                      |
| created_at                                                                              | String (Datetime)                                                      | Mandatory                                            | 2023-11-19T06:04:57-08:00                         | The timestamp for when the order was placed                                                                                                                                                                                          |
| updated_at                                                                              | String (Datetime)                                                      | Mandatory                                            | 2023-11-19T06:04:57-08:00                         | The timestamp for when the order was last updated                                                                                                                                                                                    |
| cancelled_at                                                                            | String (Datetime)                                                      | Mandatory (only for `orders_cancelled`)              | 2023-11-19T06:04:57-08:00                         | The timestamp for when the order was cancelled                                                                                                                                                                                       |
| currency                                                                                | String                                                                 | Mandatory                                            | USD                                               | Currency                                                                                                                                                                                                                             |
| email                                                                                   | String                                                                 | Mandatory (if phone and customer.id are not present) | [jeevan@lifesight.io](mailto:jeevan@lifesight.io) | Email of the customer placing the order                                                                                                                                                                                              |
| total_price                                                                             | String                                                                 | Mandatory                                            | 30.49                                             | Total Price of the order                                                                                                                                                                                                             |
| subtotal_price                                                                          | String                                                                 | Mandatory                                            | 23.4                                              | This value is for the subtotal price of all the items in the order after both line-item and cart discounts have been applied. The subtotal doesn't include taxes (unless taxes are included in the prices), shipping costs, or tips. |
| financial_status                                                                        | String                                                                 | Suggested                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| authorized, pending, paid, partially_paid, refunded, voided, partially_refunded, unpaid | Financial status of the order                                          |                                                      |                                                   |                                                                                                                                                                                                                                      |
| fulfillment_status                                                                      | String                                                                 | Suggested                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| shipped, partial, unshipped, unfulfilled                                                | Fulfillment status of the order                                        |                                                      |                                                   |                                                                                                                                                                                                                                      |
| discount_codes[*].code                                                                  | String                                                                 | Suggested                                            | SPRING30                                          | Discount code applied in the order                                                                                                                                                                                                   |
| discount_codes[*].amount                                                                | String                                                                 | Suggested                                            | 30.00                                             | Discount amount in the order                                                                                                                                                                                                         |
| discount_codes[*].type                                                                  | String                                                                 | Suggested                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| fixed_amount, percentage, shipping                                                      | Type of discount applied                                               |                                                      |                                                   |                                                                                                                                                                                                                                      |
| discount_codes[*].price_rule_id                                                         | String                                                                 | Suggested                                            | 1445602380                                        | The ID for the price rule that this discount code belongs to                                                                                                                                                                         |
| phone                                                                                   | String                                                                 | Mandatory (if email and customer.id are not present) | 9800320000                                        | Phone of the customer placing the order                                                                                                                                                                                              |
| referring_site                                                                          | String                                                                 | Suggested                                            | lifesight.io                                      | The referring site that led to the purchase                                                                                                                                                                                          |
| tags                                                                                    | String                                                                 | Suggested                                            | Loyal                                             | Order tags                                                                                                                                                                                                                           |
| customer.id                                                                             | String                                                                 | Mandatory                                            | 6980745363528                                     | ID of the customer placing the order                                                                                                                                                                                                 |
| customer.email                                                                          | String                                                                 | Mandatory                                            | [jeevan@lifesight.io](mailto:jeevan@lifesight.io) | Email of the customer placing the order                                                                                                                                                                                              |
| customer.phone                                                                          | String                                                                 | Mandatory                                            | 9800320000                                        | Phone of the customer placing the order                                                                                                                                                                                              |
| customer.first_name                                                                     | String                                                                 | Suggested                                            | Jeevan                                            | First name of the customer placing the order                                                                                                                                                                                         |
| customer.last_name                                                                      | String                                                                 | Suggested                                            | B R                                               | Last name of the customer placing the order                                                                                                                                                                                          |
| line_items[*].name                                                                      | String                                                                 | Suggested                                            | Navy Crew Neck T-Shirt - M                        | Full name of the line item in the order (Product Name + Variant)                                                                                                                                                                     |
| line_items[*].price                                                                     | String                                                                 | Mandatory                                            | 23.49                                             | Price of the line item in the order                                                                                                                                                                                                  |
| line_items[*].product_id                                                                | Integer                                                                | Mandatory                                            | 3891553173576                                     | Product ID of the line item in the order                                                                                                                                                                                             |
| line_items[*].quantity                                                                  | Integer                                                                | Mandatory                                            | 1                                                 | Quantity of the line item in the order                                                                                                                                                                                               |
| line_items[*].title                                                                     | String                                                                 | Mandatory                                            | Navy Crew Neck T-Shirt                            | Product Title of the line item in the order                                                                                                                                                                                          |
| line_items[*].total_discount                                                            | String                                                                 | Mandatory                                            | 0.00                                              | Total discount applied on the line item in the order                                                                                                                                                                                 |
| line_items[*].variant_id                                                                | Integer                                                                | Mandatory                                            | 29276034203720                                    | Variant ID of the line item in the order                                                                                                                                                                                             |
| line_items[*].variant_title                                                             | String                                                                 | Mandatory                                            | M                                                 | Variant Title of the line item in the order                                                                                                                                                                                          |
| shipping_address.city                                                                   | String                                                                 | Mandatory                                            | Swampscott                                        | City of the customer’s shipping address                                                                                                                                                                                              |
| shipping_address.zip                                                                    | String                                                                 | Mandatory                                            | 01907                                             | Postal Code/ZIP of the customer’s shipping address                                                                                                                                                                                   |
| shipping_address.province                                                               | String                                                                 | Mandatory                                            | Massachusetts                                     | Province/State of the customer’s shipping address                                                                                                                                                                                    |
| shipping_address.country                                                                | String                                                                 | Mandatory                                            | United States                                     | Country of the customer’s shipping address                                                                                                                                                                                           |
| discount_applications[*].target_selection                                               | String                                                                 | Mandatory                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| all, entitled, explicit                                                                 | The selection method for line items or shipping lines to be discounted |                                                      |                                                   |                                                                                                                                                                                                                                      |
| discount_applications[*].target_type                                                    | String                                                                 | Mandatory                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| line_item, shipping_line                                                                | The type of item that the discount applies to                          |                                                      |                                                   |                                                                                                                                                                                                                                      |
| discount_applications[*].title                                                          | String                                                                 | Mandatory                                            | SUMMER10!                                         | The customer-facing name of the discount                                                                                                                                                                                             |
| discount_applications[*].total_allocated_amount                                         | String                                                                 | Mandatory                                            | 2.51                                              | The total amount of the discount in the currency's subunit                                                                                                                                                                           |
| discount_applications[*].type                                                           | String                                                                 | Mandatory                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| automatic, discount_code, manual, script                                                | The type of the discount.                                              |                                                      |                                                   |                                                                                                                                                                                                                                      |
| discount_applications[*].value                                                          | String                                                                 | Mandatory                                            | 2.51                                              | The value of the discount.                                                                                                                                                                                                           |
| discount_applications[*].value_type                                                     | String                                                                 | Mandatory                                            | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| fixed_amount, percentage                                                                | The value type of the discount.                                        |                                                      |                                                   |                                                                                                                                                                                                                                      |
| line_items[*].discount_allocations[*].amount                                            | String                                                                 | Mandatory                                            | 2.51                                              | The amount of the discount for the particular line_item                                                                                                                                                                              |
| line_items[*].discount_allocations[*].discount_application                              | String                                                                 | Mandatory                                            | SUMMER10!                                         | The customer-facing name of the discount                                                                                                                                                                                             |

- For the `orders_create` and `orders_paid` events, `created_at` is a mandatory field
- For the `orders_updated`, `orders_fulfilled`, `orders_partially_fulfilled` events, `updated_at` is a mandatory field
- For the `orders_cancelled` event, `cancelled_at` is a mandatory field

`line_items` and `discount_codes` are Array of Objects and can have multiple objects within one array.

Example for multiple `discount_codes` (3 objects within discount_codes):

```jsx
"discount_codes": [
    {
      "code": "SPRING30",
      "amount": "30.00",
      "type": "fixed_amount"
    },
		{
      "code": "SPRING10",
      "amount": "30.00",
      "type": "percentage"
    },
		{
      "code": "FLAT5",
      "amount": "5.00",
      "type": "fixed_amount"
    }
  ]
```

Example for multiple `line_items` (2 objects within line_items):

```jsx
"line_items": [
        {
            "id": 14405811077192,
            "admin_graphql_api_id": "gid://shopify/LineItem/14405811077192",
            "attributed_staffs": [],
            "fulfillable_quantity": 1,
            "fulfillment_service": "manual",
            "fulfillment_status": null,
            "gift_card": false,
            "grams": 151,
            "name": "Navy Crew Neck T-Shirt - M",
            "pre_tax_price": "23.49",
            "pre_tax_price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "price": "23.49",
            "price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "product_exists": true,
            "product_id": 3891553173576,
            "properties": [],
            "quantity": 1,
            "requires_shipping": true,
            "sku": "LS4000NAVYM",
            "tax_code": "PC040100",
            "taxable": true,
            "title": "Navy Crew Neck T-Shirt",
            "total_discount": "0.00",
            "total_discount_set": {
                "shop_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                }
            },
            "variant_id": 29276034203720,
            "variant_inventory_management": "shopify",
            "variant_title": "M",
            "vendor": "Lifesight",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "duties": [],
            "discount_allocations": []
        },
        {
            "id": 14405811077193,
            "admin_graphql_api_id": "gid://shopify/LineItem/14405811077193",
            "attributed_staffs": [],
            "fulfillable_quantity": 1,
            "fulfillment_service": "manual",
            "fulfillment_status": null,
            "gift_card": false,
            "grams": 151,
            "name": "Navy Crew Neck T-Shirt - L",
            "pre_tax_price": "24.49",
            "pre_tax_price_set": {
                "shop_money": {
                    "amount": "24.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "24.49",
                    "currency_code": "USD"
                }
            },
            "price": "24.49",
            "price_set": {
                "shop_money": {
                    "amount": "24.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "24.49",
                    "currency_code": "USD"
                }
            },
            "product_exists": true,
            "product_id": 3891553173576,
            "properties": [],
            "quantity": 1,
            "requires_shipping": true,
            "sku": "LS4000NAVYM",
            "tax_code": "PC040100",
            "taxable": true,
            "title": "Navy Crew Neck T-Shirt",
            "total_discount": "0.00",
            "total_discount_set": {
                "shop_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                }
            },
            "variant_id": 29276034203721,
            "variant_inventory_management": "shopify",
            "variant_title": "L",
            "vendor": "Lifesight",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "duties": [],
            "discount_allocations": []
        }
    ]
```

### Example Payload for Orders Object

```json
{
    "id": 5766207635539,
    "admin_graphql_api_id": "gid://shopify/Order/5766207635539",
    "app_id": 2329312,
    "browser_ip": null,
    "buyer_accepts_marketing": true,
    "cancel_reason": null,
    "cancelled_at": null,
    "cart_token": null,
    "checkout_id": 40082301255752,
    "checkout_token": "f4a6496368e91080bf4bb0a809195f95",
    "client_details": {
        "accept_language": "",
        "browser_height": null,
        "browser_ip": null,
        "browser_width": null,
        "session_hash": null,
        "user_agent": ""
    },
    "closed_at": null,
    "company": null,
    "confirmation_number": "896997838783630,6790791201038369",
    "confirmed": true,
    "contact_email": "jeevan@lifesight.io",
    "created_at": "2023-11-19T06:04:57-08:00",
    "currency": "USD",
    "current_subtotal_price": "23.49",
    "current_subtotal_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "current_total_additional_fees_set": null,
    "current_total_discounts": "0.00",
    "current_total_discounts_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "current_total_duties_set": null,
    "current_total_price": "30.49",
    "current_total_price_set": {
        "shop_money": {
            "amount": "30.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "30.49",
            "currency_code": "USD"
        }
    },
    "current_total_tax": "0.00",
    "current_total_tax_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "customer_locale": "en",
    "device_id": null,
    "discount_codes": [],
    "email": "jeevan@lifesight.io",
    "estimated_taxes": false,
    "financial_status": "paid",
    "fulfillment_status": null,
    "landing_site": "/admin/api/2023-04/checkouts.json",
    "landing_site_ref": null,
    "location_id": null,
    "merchant_of_record_app_id": null,
    "name": "#5187793",
    "note": "",
    "note_attributes": [
        {
            "name": "Channel",
            "value": "Instagram"
        },
        {
            "name": "Facebook Order ID",
            "value": "896997838783630"
        }
    ],
    "number": 5186793,
    "order_number": 5187793,
    "order_status_url": "https://trueclassictees-com.myshopify.com/22040084552/orders/38f00dfd83b526b35c64b31b7495ecf2/authenticate?key=ea48f888fefe7bca7df3009a27234700",
    "original_total_additional_fees_set": null,
    "original_total_duties_set": null,
    "payment_gateway_names": [
        "shopify_payments",
        "manual"
    ],
    "phone": null,
    "po_number": null,
    "presentment_currency": "USD",
    "processed_at": "2023-11-19T06:04:57-08:00",
    "reference": null,
    "referring_site": null,
    "source_identifier": "896997838783630,6790791201038369",
    "source_name": "2329312",
    "source_url": null,
    "subtotal_price": "23.49",
    "subtotal_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "tags": "nofraud_pass",
    "tax_exempt": false,
    "tax_lines": [],
    "taxes_included": false,
    "test": false,
    "token": "38f00dfd83b526b35c64b31b7495ecf2",
    "total_discounts": "0.00",
    "total_discounts_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "total_line_items_price": "23.49",
    "total_line_items_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "total_outstanding": "0.00",
    "total_price": "30.49",
    "total_price_set": {
        "shop_money": {
            "amount": "30.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "30.49",
            "currency_code": "USD"
        }
    },
    "total_shipping_price_set": {
        "shop_money": {
            "amount": "7.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "7.00",
            "currency_code": "USD"
        }
    },
    "total_tax": "0.00",
    "total_tax_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "total_tip_received": "0.00",
    "total_weight": 150,
    "updated_at": "2023-11-19T06:06:18-08:00",
    "user_id": null,
    "billing_address": {
        "first_name": "Jeevan",
        "address1": "100 Pacific Ave",
        "phone": null,
        "city": "Swampscott",
        "zip": "01907",
        "province": "Massachusetts",
        "country": "United States",
        "last_name": "B R",
        "address2": "",
        "company": "",
        "latitude": 42.4704092,
        "longitude": -70.89442090000001,
        "name": "Jeevan B R",
        "country_code": "US",
        "province_code": "MA"
    },
    "customer": {
        "id": 6980745363528,
        "email": "jeevan@lifesight.io",
        "accepts_marketing": true,
        "created_at": "2023-11-19T06:04:35-08:00",
        "updated_at": "2023-11-19T06:06:21-08:00",
        "first_name": "Jeevan",
        "last_name": "B R",
        "state": "disabled",
        "note": null,
        "verified_email": true,
        "multipass_identifier": null,
        "tax_exempt": false,
        "phone": null,
        "email_marketing_consent": {
            "state": "subscribed",
            "opt_in_level": "single_opt_in",
            "consent_updated_at": "2023-11-19T06:04:35-08:00"
        },
        "sms_marketing_consent": null,
        "tags": "",
        "currency": "USD",
        "accepts_marketing_updated_at": "2023-11-19T06:04:35-08:00",
        "marketing_opt_in_level": "single_opt_in",
        "tax_exemptions": [],
        "admin_graphql_api_id": "gid://shopify/Customer/6980745363528",
        "default_address": {
            "id": 8798466113608,
            "customer_id": 6980745363528,
            "first_name": "Jeevan",
            "last_name": "B R",
            "company": "",
            "address1": "100 Pacific Ave",
            "address2": "",
            "city": "Swampscott",
            "province": "Massachusetts",
            "country": "United States",
            "zip": "01907",
            "phone": null,
            "name": "Jeevan B R",
            "province_code": "MA",
            "country_code": "US",
            "country_name": "United States",
            "default": true
        }
    },
    "discount_applications": [],
    "fulfillments": [],
    "line_items": [
        {
            "id": 14405811077192,
            "admin_graphql_api_id": "gid://shopify/LineItem/14405811077192",
            "attributed_staffs": [],
            "fulfillable_quantity": 1,
            "fulfillment_service": "manual",
            "fulfillment_status": null,
            "gift_card": false,
            "grams": 151,
            "name": "Navy Crew Neck T-Shirt - M",
            "pre_tax_price": "23.49",
            "pre_tax_price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "price": "23.49",
            "price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "product_exists": true,
            "product_id": 3891553173576,
            "properties": [],
            "quantity": 1,
            "requires_shipping": true,
            "sku": "LST4000NAVYM",
            "tax_code": "PC040100",
            "taxable": true,
            "title": "Navy Crew Neck T-Shirt",
            "total_discount": "0.00",
            "total_discount_set": {
                "shop_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                }
            },
            "variant_id": 29276034203720,
            "variant_inventory_management": "shopify",
            "variant_title": "M",
            "vendor": "Lifesight",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "duties": [],
            "discount_allocations": []
        }
    ],
    "payment_terms": null,
    "refunds": [],
    "shipping_address": {
        "first_name": "Jeevan",
        "address1": "100 Pacific Ave",
        "phone": null,
        "city": "Swampscott",
        "zip": "01907",
        "province": "Massachusetts",
        "country": "United States",
        "last_name": "B R",
        "address2": "",
        "company": "",
        "latitude": 42.4704092,
        "longitude": -70.89442090000001,
        "name": "Jeevan B R",
        "country_code": "US",
        "province_code": "MA"
    },
    "shipping_lines": [
        {
            "id": 4904563769416,
            "carrier_identifier": null,
            "code": "Standard (2-9 Business Days)",
            "discounted_price": "7.00",
            "discounted_price_set": {
                "shop_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                }
            },
            "phone": null,
            "price": "7.00",
            "price_set": {
                "shop_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                }
            },
            "requested_fulfillment_service_id": null,
            "source": "shopify",
            "title": "Standard (2-9 Business Days)",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "discount_allocations": []
        }
    ]
}
```

### Example API Request

```java
curl --location 'https://moda-transform-webhook-data-prd-7jirubb0.uc.gateway.dev/transform-webhook-data?key=AIzaSyCEeXcrMmdSQP_T82Ip-VckCpgSWplPjKI&workspace={{workspace}}&source={{source}}&event_name=orders_create' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": 5766207635539,
    "admin_graphql_api_id": "gid://shopify/Order/5766207635539",
    "app_id": 2329312,
    "browser_ip": null,
    "buyer_accepts_marketing": true,
    "cancel_reason": null,
    "cancelled_at": null,
    "cart_token": null,
    "checkout_id": 40082301255752,
    "checkout_token": "f4a6496368e91080bf4bb0a809195f95",
    "client_details": {
        "accept_language": "",
        "browser_height": null,
        "browser_ip": null,
        "browser_width": null,
        "session_hash": null,
        "user_agent": ""
    },
    "closed_at": null,
    "company": null,
    "confirmation_number": "896997838783630,6790791201038369",
    "confirmed": true,
    "contact_email": "jeevan@lifesight.io",
    "created_at": "2023-11-19T06:04:57-08:00",
    "currency": "USD",
    "current_subtotal_price": "23.49",
    "current_subtotal_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "current_total_additional_fees_set": null,
    "current_total_discounts": "0.00",
    "current_total_discounts_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "current_total_duties_set": null,
    "current_total_price": "30.49",
    "current_total_price_set": {
        "shop_money": {
            "amount": "30.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "30.49",
            "currency_code": "USD"
        }
    },
    "current_total_tax": "0.00",
    "current_total_tax_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "customer_locale": "en",
    "device_id": null,
    "discount_codes": [],
    "email": "jeevan@lifesight.io",
    "estimated_taxes": false,
    "financial_status": "paid",
    "fulfillment_status": null,
    "landing_site": "/admin/api/2023-04/checkouts.json",
    "landing_site_ref": null,
    "location_id": null,
    "merchant_of_record_app_id": null,
    "name": "#5187793",
    "note": "",
    "note_attributes": [
        {
            "name": "Channel",
            "value": "Instagram"
        },
        {
            "name": "Facebook Order ID",
            "value": "896997838783630"
        }
    ],
    "number": 5186793,
    "order_number": 5187793,
    "order_status_url": "https://trueclassictees-com.myshopify.com/22040084552/orders/38f00dfd83b526b35c64b31b7495ecf2/authenticate?key=ea48f888fefe7bca7df3009a27234700",
    "original_total_additional_fees_set": null,
    "original_total_duties_set": null,
    "payment_gateway_names": [
        "shopify_payments",
        "manual"
    ],
    "phone": null,
    "po_number": null,
    "presentment_currency": "USD",
    "processed_at": "2023-11-19T06:04:57-08:00",
    "reference": null,
    "referring_site": null,
    "source_identifier": "896997838783630,6790791201038369",
    "source_name": "2329312",
    "source_url": null,
    "subtotal_price": "23.49",
    "subtotal_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "tags": "nofraud_pass",
    "tax_exempt": false,
    "tax_lines": [],
    "taxes_included": false,
    "test": false,
    "token": "38f00dfd83b526b35c64b31b7495ecf2",
    "total_discounts": "0.00",
    "total_discounts_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "total_line_items_price": "23.49",
    "total_line_items_price_set": {
        "shop_money": {
            "amount": "23.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "23.49",
            "currency_code": "USD"
        }
    },
    "total_outstanding": "0.00",
    "total_price": "30.49",
    "total_price_set": {
        "shop_money": {
            "amount": "30.49",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "30.49",
            "currency_code": "USD"
        }
    },
    "total_shipping_price_set": {
        "shop_money": {
            "amount": "7.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "7.00",
            "currency_code": "USD"
        }
    },
    "total_tax": "0.00",
    "total_tax_set": {
        "shop_money": {
            "amount": "0.00",
            "currency_code": "USD"
        },
        "presentment_money": {
            "amount": "0.00",
            "currency_code": "USD"
        }
    },
    "total_tip_received": "0.00",
    "total_weight": 150,
    "updated_at": "2023-11-19T06:06:18-08:00",
    "user_id": null,
    "billing_address": {
        "first_name": "Jeevan",
        "address1": "100 Pacific Ave",
        "phone": null,
        "city": "Swampscott",
        "zip": "01907",
        "province": "Massachusetts",
        "country": "United States",
        "last_name": "B R",
        "address2": "",
        "company": "",
        "latitude": 42.4704092,
        "longitude": -70.89442090000001,
        "name": "Jeevan B R",
        "country_code": "US",
        "province_code": "MA"
    },
    "customer": {
        "id": 6980745363528,
        "email": "jeevan@lifesight.io",
        "accepts_marketing": true,
        "created_at": "2023-11-19T06:04:35-08:00",
        "updated_at": "2023-11-19T06:06:21-08:00",
        "first_name": "Jeevan",
        "last_name": "B R",
        "state": "disabled",
        "note": null,
        "verified_email": true,
        "multipass_identifier": null,
        "tax_exempt": false,
        "phone": null,
        "email_marketing_consent": {
            "state": "subscribed",
            "opt_in_level": "single_opt_in",
            "consent_updated_at": "2023-11-19T06:04:35-08:00"
        },
        "sms_marketing_consent": null,
        "tags": "",
        "currency": "USD",
        "accepts_marketing_updated_at": "2023-11-19T06:04:35-08:00",
        "marketing_opt_in_level": "single_opt_in",
        "tax_exemptions": [],
        "admin_graphql_api_id": "gid://shopify/Customer/6980745363528",
        "default_address": {
            "id": 8798466113608,
            "customer_id": 6980745363528,
            "first_name": "Jeevan",
            "last_name": "B R",
            "company": "",
            "address1": "100 Pacific Ave",
            "address2": "",
            "city": "Swampscott",
            "province": "Massachusetts",
            "country": "United States",
            "zip": "01907",
            "phone": null,
            "name": "Jeevan B R",
            "province_code": "MA",
            "country_code": "US",
            "country_name": "United States",
            "default": true
        }
    },
    "discount_applications": [],
    "fulfillments": [],
    "line_items": [
        {
            "id": 14405811077192,
            "admin_graphql_api_id": "gid://shopify/LineItem/14405811077192",
            "attributed_staffs": [],
            "fulfillable_quantity": 1,
            "fulfillment_service": "manual",
            "fulfillment_status": null,
            "gift_card": false,
            "grams": 151,
            "name": "Navy Crew Neck T-Shirt - M",
            "pre_tax_price": "23.49",
            "pre_tax_price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "price": "23.49",
            "price_set": {
                "shop_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "23.49",
                    "currency_code": "USD"
                }
            },
            "product_exists": true,
            "product_id": 3891553173576,
            "properties": [],
            "quantity": 1,
            "requires_shipping": true,
            "sku": "LST4000NAVYM",
            "tax_code": "PC040100",
            "taxable": true,
            "title": "Navy Crew Neck T-Shirt",
            "total_discount": "0.00",
            "total_discount_set": {
                "shop_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "0.00",
                    "currency_code": "USD"
                }
            },
            "variant_id": 29276034203720,
            "variant_inventory_management": "shopify",
            "variant_title": "M",
            "vendor": "Lifesight",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "duties": [],
            "discount_allocations": []
        }
    ],
    "payment_terms": null,
    "refunds": [],
    "shipping_address": {
        "first_name": "Jeevan",
        "address1": "100 Pacific Ave",
        "phone": null,
        "city": "Swampscott",
        "zip": "01907",
        "province": "Massachusetts",
        "country": "United States",
        "last_name": "B R",
        "address2": "",
        "company": "",
        "latitude": 42.4704092,
        "longitude": -70.89442090000001,
        "name": "Jeevan B R",
        "country_code": "US",
        "province_code": "MA"
    },
    "shipping_lines": [
        {
            "id": 4904563769416,
            "carrier_identifier": null,
            "code": "Standard (2-9 Business Days)",
            "discounted_price": "7.00",
            "discounted_price_set": {
                "shop_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                }
            },
            "phone": null,
            "price": "7.00",
            "price_set": {
                "shop_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                },
                "presentment_money": {
                    "amount": "7.00",
                    "currency_code": "USD"
                }
            },
            "requested_fulfillment_service_id": null,
            "source": "shopify",
            "title": "Standard (2-9 Business Days)",
            "tax_lines": [
                {
                    "channel_liable": true,
                    "price": "0.00",
                    "price_set": {
                        "shop_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        },
                        "presentment_money": {
                            "amount": "0.00",
                            "currency_code": "USD"
                        }
                    },
                    "rate": 0.0,
                    "title": "MASSACHUSETTS Sales and Use Tax"
                }
            ],
            "discount_allocations": []
        }
    ]
}'
```

## Checkouts

All checkout events would have the same payload structure. These events include `checkouts_create` and `checkouts_update`. The event to be sent is to be specified in the `event_name` query parameter in the API request.

### Mandatory and Suggested Fields in the Checkouts Payload

| Field                              | Data Type                | Mandatory/Suggested                 | Sample Value                                      | Description                                                                                                                                                                                                                          |
| ---------------------------------- | ------------------------ | ----------------------------------- | ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                                 | Integer                  | Mandatory                           | 37112239489314                                    | ID of the Checkout                                                                                                                                                                                                                   |
| created_at                         | String (Datetime)        | Mandatory                           | 2023-11-19T06:04:57-08:00                         | The timestamp for when the checkout was placed                                                                                                                                                                                       |
| updated_at                         | String (Datetime)        | Mandatory                           | 2023-11-19T06:04:57-08:00                         | The timestamp for when the checkout was last updated                                                                                                                                                                                 |
| currency                           | String                   | Mandatory                           | USD                                               | Currency                                                                                                                                                                                                                             |
| email                              | String                   | Mandatory (if phone is not present) | [jeevan@lifesight.io](mailto:jeevan@lifesight.io) | Email of the customer creating the checkout                                                                                                                                                                                          |
| total_price                        | String                   | Mandatory                           | 30.49                                             | Total Price of the checkout                                                                                                                                                                                                          |
| subtotal_price                     | String                   | Mandatory                           | 23.4                                              | This value is for the subtotal price of all the items in the order after both line-item and cart discounts have been applied. The subtotal doesn't include taxes (unless taxes are included in the prices), shipping costs, or tips. |
| discount_codes[*].code             | String                   | Suggested                           | SPRING30                                          | Discount code applied in the checkout                                                                                                                                                                                                |
| discount_codes[*].amount           | String                   | Suggested                           | 30.00                                             | Discount amount in the checkout                                                                                                                                                                                                      |
| discount_codes[*].type             | String                   | Suggested                           | POSSIBLE VALUES:                                  |                                                                                                                                                                                                                                      |
| fixed_amount, percentage, shipping | Type of discount applied |                                     |                                                   |                                                                                                                                                                                                                                      |
| phone                              | String                   | Mandatory (if email is not present) | 9800320000                                        | Phone of the customer creating the checkout                                                                                                                                                                                          |
| referring_site                     | String                   | Suggested                           | lifesight.io                                      | The referring site that led to the checkout                                                                                                                                                                                          |
| line_items[*].name                 | String                   | Suggested                           | Navy Crew Neck T-Shirt - M                        | Full name of the line item in the checkout (Product Name + Variant)                                                                                                                                                                  |
| line_items[*].price                | String                   | Mandatory                           | 23.49                                             | Price of the line item in the checkout                                                                                                                                                                                               |
| line_items[*].product_id           | Integer                  | Mandatory                           | 3891553173576                                     | Product ID of the line item in the checkout                                                                                                                                                                                          |
| line_items[*].quantity             | Integer                  | Mandatory                           | 1                                                 | Quantity of the line item in the checkout                                                                                                                                                                                            |
| line_items[*].title                | String                   | Mandatory                           | Navy Crew Neck T-Shirt                            | Product Title of the line item in the checkout                                                                                                                                                                                       |
| line_items[*].total_discount       | String                   | Mandatory                           | 0.00                                              | Total discount applied on the line item in the checkout                                                                                                                                                                              |
| line_items[*].variant_id           | Integer                  | Mandatory                           | 29276034203720                                    | Variant ID of the line item in the checkout                                                                                                                                                                                          |
| line_items[*].variant_title        | String                   | Mandatory                           | M                                                 | Variant Title of the line item in the checkout                                                                                                                                                                                       |
| shipping_address.city              | String                   | Mandatory                           | Swampscott                                        | City of the customer’s shipping address                                                                                                                                                                                              |
| shipping_address.zip               | String                   | Mandatory                           | 01907                                             | Postal Code/ZIP of the customer’s shipping address                                                                                                                                                                                   |
| shipping_address.province          | String                   | Mandatory                           | Massachusetts                                     | Province/State of the customer’s shipping address                                                                                                                                                                                    |
| shipping_address.country           | String                   | Mandatory                           | United States                                     | Country of the customer’s shipping address                                                                                                                                                                                           |

### Example Payload for Checkouts Object

```jsx
{
    "id": 37112239489315,
    "token": "da4a9d115469c72cf166bfbe6c5313d1",
    "cart_token": "Z2NwLXVzLWNlbnRyYWwxOjAxSEdGRkRGQkZUQ0dXQ0gwRjJaWkFNTU1N",
    "email": "jeevan@lifesight.io",
    "gateway": null,
    "buyer_accepts_marketing": false,
    "buyer_accepts_sms_marketing": false,
    "sms_marketing_phone": null,
    "created_at": "2023-11-30T06:42:16+00:00",
    "updated_at": "2023-11-30T01:43:48-05:00",
    "landing_site": "/checkouts/cn/0c6778120e464ffcbd78a9d57126e046/thank_you",
    "note": "",
    "note_attributes":
    [],
    "referring_site": "https://moda-pixel-testing.myshopify.com/",
    "shipping_lines":
    [],
    "shipping_address":
    [],
    "taxes_included": false,
    "total_weight": 580,
    "currency": "SGD",
    "completed_at": null,
    "phone": null,
    "customer_locale": "en-SG",
    "line_items":
    [
        {
            "key": "45902754185506",
            "fulfillment_service": "manual",
            "gift_card": false,
            "grams": 580,
            "presentment_title": "Reddy Grey & Navy Ceramic & Bamboo Elevated Dog Double Diner",
            "presentment_variant_title": "",
            "product_id": 8448447512866,
            "quantity": 1,
            "requires_shipping": true,
            "sku": "Reddy-Bamboo-Bowl",
            "taxable": true,
            "title": "Reddy Grey & Navy Ceramic & Bamboo Elevated Dog Double Diner",
            "variant_id": 45902754185506,
            "variant_title": "",
            "variant_price": "23.99",
            "vendor": "Reddy",
            "unit_price_measurement":
            {
                "measured_type": null,
                "quantity_value": null,
                "quantity_unit": null,
                "reference_value": null,
                "reference_unit": null
            },
            "compare_at_price": "28.99",
            "line_price": "23.99",
            "price": "23.99",
            "applied_discounts":
            [],
            "destination_location_id": null,
            "user_id": null,
            "rank": null,
            "origin_location_id": null,
            "properties": null
        }
    ],
    "name": "#37112239489315",
    "abandoned_checkout_url": "https://moda-pixel-testing.myshopify.com/80371122466/checkouts/ac/Z2NwLXVzLWNlbnRyYWwxOjAxSEdGRkRGQkZUQ0dXQ0gwRjJaWkFNTU1N/recover?key=fb805739459d0254710146f3c92a610a",
    "discount_codes":
    [],
    "tax_lines":
    [
        {
            "price": "1.92",
            "rate": 0.08,
            "title": "GST"
        }
    ],
    "presentment_currency": "SGD",
    "source_name": "web",
    "total_line_items_price": "23.99",
    "total_tax": "1.92",
    "total_discounts": "0.00",
    "subtotal_price": "23.99",
    "total_price": "25.91",
    "total_duties": "0.00",
    "device_id": null,
    "user_id": null,
    "location_id": null,
    "source_identifier": null,
    "source_url": null,
    "source": null,
    "closed_at": null
}
```

### Example API Request

```jsx
curl --location 'https://moda-transform-webhook-data-prd-7jirubb0.uc.gateway.dev/transform-webhook-data?key=AIzaSyCEeXcrMmdSQP_T82Ip-VckCpgSWplPjKI&{{workspace}}&source={{source}}event_name=checkouts_create' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": 37112239489315,
    "token": "da4a9d115469c72cf166bfbe6c5313d1",
    "cart_token": "Z2NwLXVzLWNlbnRyYWwxOjAxSEdGRkRGQkZUQ0dXQ0gwRjJaWkFNTU1N",
    "email": "jeevan@lifesight.io",
    "gateway": null,
    "buyer_accepts_marketing": false,
    "buyer_accepts_sms_marketing": false,
    "sms_marketing_phone": null,
    "created_at": "2023-11-30T06:42:16+00:00",
    "updated_at": "2023-11-30T01:43:48-05:00",
    "landing_site": "/checkouts/cn/0c6778120e464ffcbd78a9d57126e046/thank_you",
    "note": "",
    "note_attributes":
    [],
    "referring_site": "https://moda-pixel-testing.myshopify.com/",
    "shipping_lines":
    [],
    "shipping_address":
    [],
    "taxes_included": false,
    "total_weight": 580,
    "currency": "SGD",
    "completed_at": null,
    "phone": null,
    "customer_locale": "en-SG",
    "line_items":
    [
        {
            "key": "45902754185506",
            "fulfillment_service": "manual",
            "gift_card": false,
            "grams": 580,
            "presentment_title": "Reddy Grey & Navy Ceramic & Bamboo Elevated Dog Double Diner",
            "presentment_variant_title": "",
            "product_id": 8448447512866,
            "quantity": 1,
            "requires_shipping": true,
            "sku": "Reddy-Bamboo-Bowl",
            "taxable": true,
            "title": "Reddy Grey & Navy Ceramic & Bamboo Elevated Dog Double Diner",
            "variant_id": 45902754185506,
            "variant_title": "",
            "variant_price": "23.99",
            "vendor": "Reddy",
            "unit_price_measurement":
            {
                "measured_type": null,
                "quantity_value": null,
                "quantity_unit": null,
                "reference_value": null,
                "reference_unit": null
            },
            "compare_at_price": "28.99",
            "line_price": "23.99",
            "price": "23.99",
            "applied_discounts":
            [],
            "destination_location_id": null,
            "user_id": null,
            "rank": null,
            "origin_location_id": null,
            "properties": null
        }
    ],
    "name": "#37112239489315",
    "abandoned_checkout_url": "https://moda-pixel-testing.myshopify.com/80371122466/checkouts/ac/Z2NwLXVzLWNlbnRyYWwxOjAxSEdGRkRGQkZUQ0dXQ0gwRjJaWkFNTU1N/recover?key=fb805739459d0254710146f3c92a610a",
    "discount_codes":
    [],
    "tax_lines":
    [
        {
            "price": "1.92",
            "rate": 0.08,
            "title": "GST"
        }
    ],
    "presentment_currency": "SGD",
    "source_name": "web",
    "total_line_items_price": "23.99",
    "total_tax": "1.92",
    "total_discounts": "0.00",
    "subtotal_price": "23.99",
    "total_price": "25.91",
    "total_duties": "0.00",
    "device_id": null,
    "user_id": null,
    "location_id": null,
    "source_identifier": null,
    "source_url": null,
    "source": null,
    "closed_at": null
}'
```

## Customers

All customer events would have the same payload structure. These events include `customers_create` and `customers_update`. The event to be sent is to be specified in the `event_name` query parameter in the API request.

### Mandatory and Suggested Fields in the Customers Payload

| Field        | Data Type         | Mandatory/Suggested                 | Sample Value                                      | Description                                          |
| ------------ | ----------------- | ----------------------------------- | ------------------------------------------------- | ---------------------------------------------------- |
| id           | Integer           | Mandatory                           | 7677484597542                                     | ID of the Customer                                   |
| created_at   | String (Datetime) | Mandatory                           | 2023-11-19T06:04:57-08:00                         | The timestamp for when the customer was created      |
| updated_at   | String (Datetime) | Mandatory                           | 2023-11-19T06:04:57-08:00                         | The timestamp for when the customer was last updated |
| currency     | String            | Suggested                           | USD                                               | Currency                                             |
| email        | String            | Mandatory (if phone is not present) | [jeevan@lifesight.io](mailto:jeevan@lifesight.io) | Email of the customer                                |
| orders_count | Integer           | Suggested                           | 1                                                 | Count of orders placed by the customer               |
| total_spent  | String            | Suggested                           | 10.00                                             | Total spent by the customer                          |
| tags         | String            | Suggested                           | Loyal                                             | Customer tags                                        |
| phone        | String            | Mandatory (if email is not present) | 9800320000                                        | Phone of the customer                                |

### Example Payload for Customers Object

```jsx
{
    "id": 7677484597543,
    "email": "jeevan@lifesight.io",
    "accepts_marketing": false,
    "created_at": "2023-12-01T06:44:57-05:00",
    "updated_at": "2023-12-01T06:44:57-05:00",
    "first_name": "Jeevan",
    "last_name": "B R",
    "orders_count": 0,
    "state": "enabled",
    "total_spent": "0.00",
    "last_order_id": null,
    "note": null,
    "verified_email": false,
    "multipass_identifier": null,
    "tax_exempt": false,
    "tags": "",
    "last_order_name": null,
    "currency": "SGD",
    "phone": null,
    "addresses":
    [
        {
            "id": 9881955336486,
            "customer_id": 7677484597543,
            "first_name": "Jeevan",
            "last_name": "h",
            "company": null,
            "address1": null,
            "address2": null,
            "city": "Singapore",
            "province": null,
            "country": "Singapore",
            "zip": null,
            "phone": null,
            "name": "Jeevan B R",
            "province_code": null,
            "country_code": "SG",
            "country_name": "Singapore",
            "default": true
        }
    ],
    "accepts_marketing_updated_at": "2023-12-01T06:44:57-05:00",
    "marketing_opt_in_level": null,
    "tax_exemptions":
    [],
    "email_marketing_consent":
    {
        "state": "not_subscribed",
        "opt_in_level": "single_opt_in",
        "consent_updated_at": null
    },
    "sms_marketing_consent": null,
    "admin_graphql_api_id": "gid://shopify/Customer/7677484597543",
    "default_address":
    {
        "id": 9881955336486,
        "customer_id": 7677484597543,
        "first_name": "Jeevan",
        "last_name": "B R",
        "company": null,
        "address1": null,
        "address2": null,
        "city": "Singapore",
        "province": null,
        "country": "Singapore",
        "zip": null,
        "phone": null,
        "name": "Jeevan B R",
        "province_code": null,
        "country_code": "SG",
        "country_name": "Singapore",
        "default": true
    }
}
```

### Example API Request

```jsx
curl --location 'https://moda-transform-webhook-data-prd-7jirubb0.uc.gateway.dev/transform-webhook-data?key=AIzaSyCEeXcrMmdSQP_T82Ip-VckCpgSWplPjKI&{{workspace}}&source={{source}}&event_name=customers_create' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": 7677484597543,
    "email": "jeevan@lifesight.io",
    "accepts_marketing": false,
    "created_at": "2023-12-01T06:44:57-05:00",
    "updated_at": "2023-12-01T06:44:57-05:00",
    "first_name": "Jeevan",
    "last_name": "B R",
    "orders_count": 0,
    "state": "enabled",
    "total_spent": "0.00",
    "last_order_id": null,
    "note": null,
    "verified_email": false,
    "multipass_identifier": null,
    "tax_exempt": false,
    "tags": "",
    "last_order_name": null,
    "currency": "SGD",
    "phone": null,
    "addresses":
    [
        {
            "id": 9881955336486,
            "customer_id": 7677484597543,
            "first_name": "Jeevan",
            "last_name": "h",
            "company": null,
            "address1": null,
            "address2": null,
            "city": "Singapore",
            "province": null,
            "country": "Singapore",
            "zip": null,
            "phone": null,
            "name": "Jeevan B R",
            "province_code": null,
            "country_code": "SG",
            "country_name": "Singapore",
            "default": true
        }
    ],
    "accepts_marketing_updated_at": "2023-12-01T06:44:57-05:00",
    "marketing_opt_in_level": null,
    "tax_exemptions":
    [],
    "email_marketing_consent":
    {
        "state": "not_subscribed",
        "opt_in_level": "single_opt_in",
        "consent_updated_at": null
    },
    "sms_marketing_consent": null,
    "admin_graphql_api_id": "gid://shopify/Customer/7677484597543",
    "default_address":
    {
        "id": 9881955336486,
        "customer_id": 7677484597543,
        "first_name": "Jeevan",
        "last_name": "h",
        "company": null,
        "address1": null,
        "address2": null,
        "city": "Singapore",
        "province": null,
        "country": "Singapore",
        "zip": null,
        "phone": null,
        "name": "Jeevan B R",
        "province_code": null,
        "country_code": "SG",
        "country_name": "Singapore",
        "default": true
    }
}'
```