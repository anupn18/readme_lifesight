---
title: How to setup Lifesight SDK using GTM Container
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
Lifesight provides a customized JS SDK that users can effortlessly integrate into their website via the GTM container approach. The client will have the freedom to track the event he wants and how he wants. [although there is some limitations like web schema should be ready to consume any new fields]

<br />

We also provide the customers with custom APIs (functions) that they can configure for their website in alignment with their tracking plan & ultimately initiate the transmission of client-side event stream data to our backend server.

The user imports the Lifesight container into their GTM account and will get all the Lifesight tags, triggers and variables. The prerequisite is that they have the dataLayer setup. else they set it up and reconfigure the variables and tags which would be relatively easier.

### **In case you are not familiar with the Google GTM terms**

<Image align="center" src="https://files.readme.io/9a8407b62782e61cf30038dea96aed27530e92910158fa65c6e415ad59354e5b-Nov_21_Screenshot_from_Notion.png" />


Standard E-commerce Events 

| **SDK Events**          |   |
| ----------------------- | - |
| `page_view`             |   |
| `product_list_view`     |   |
| `product_view`          |   |
| `product_image_clicked` |   |
| `add_to_cart`           |   |
| `cart_view`             |   |
| `remove_from_cart`\*    |   |
| `thank_you_page_view`   |   |
| `product_searched`\*    |   |
| `~~variants_view~~`     |   |
| `product_shared`\*      |   |
| `active_on_store`\*     |   |
|                         |   |
| Form_submit             |   |

For each of the above events, we should create variables, tags and triggers according to Lifesight standard data layer structure. 

## Lifesight DataLayer [*WIP*]

The implementation team should help the client set up e-commerce events in the dataLayer in an ordered manner for our custom SDK to work using the import container approach.

Note: If the customer already has e-commerce events set up in the data layer, but in a different fashion they can still import our lifesight container and then update the variables and triggers according to their setup of the datalayer. 

**When implementing these data layer pushes for the client, ensure that they are executed in the correct context: [IMP]**

- **`page_view`** when the page loads.
- **`product_list_view`** when a list of products are viewed, typically on category pages or search result pages.
- **`product_view`** when an individual product page is viewed.
- **`product_image_clicked`** when a user clicks on an image of a product.
- **`add_to_cart`** when a product is added to the shopping cart.
- **`cart_view`** when the shopping cart page is viewed.

### **page_view**

option 1: It gets captured by default unless it is SPA. [So client need not setup this call explicitly unless he wants to capture spa or some additional fields in the payload]

option2: make the event in dataLayer as well

reasons: will this help in SPA 

```jsx
{
    "event": "view_item_list",
    "ecommerce": {
       page: {
					    path: "/path-of-the-current-page",
					    title: "Title of the current page",
					    url: "https://www.example.com/path-of-the-current-page",
              referrer: "",
					    search: "?utm_source=instagram&utm_medium=social-ad&utm_campaign=i      gproductlaunch0323",
					    // ... any other page-level data you might want to track
					  },
       
    },     
    "gtm.uniqueEventId": 69
}
```

### **product_view**

```jsx
{
    "event": "view_item",
    "ecommerce": {
        "currency": "INR",
        "items": [
            {
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "inventory_status": {status of inventory eg) 'in stock'} //TBA
            }
        ]
    },
    "gtm.uniqueEventId": 51
}

```

### **product_list_view**

Option 1 - Current shopify approach:  
No data passed so we can just trigger the event based on page (Event without any product data)

```jsx
{
    "event": "view_item_list",
    "ecommerce": {
        "item_list_id": {Product List Id}, // TBA
        "item_list_name": {Product List collection Name eg) New arrivals/ Makeup //TBA
    },     
    "gtm.uniqueEventId": 69
}
```

Option 2 - Show a list of all products or few products in that list page

```jsx
myglamm

{
    "event": "view_item_list",
    "ecommerce": {
        "item_list_id": {Product List Id},
        "item_list_name": {Product List collection Name eg) New arrivals // TBA 
        "items": [
            {
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "item_index": {Item index in the list eg)0 } //TBA
                "inventory_status": {status of inventory eg) 'in stock'} //TBA
            },
            {
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "item_index": {Item index in the list eg)0 } //TBA
                "inventory_status": {status of inventory eg) 'in stock'} //TBA
            },
           //more products if they are in the list 
        ]
    },
    "gtm.uniqueEventId": 37
}
```

### **product_image_clicked**

```jsx
{
    "event": "view_item_image",
    "ecommerce": {
        "currency": "INR",
        "items": [
            {
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "inventory_status": {status of inventory eg) 'in stock'} //TBA
            }
        ]
    },
    "gtm.uniqueEventId": 51
}

```

### **add_to_cart**

```jsx
{
    "event": "add_to_cart",
    "ecommerce": {
        "currency": "INR",
        "value": 384, // to keep or not keep 
        "items": [
            {
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "item_quantity": {Product Qnt Added} // TBA
            }
        ]
    },
    "gtm.uniqueEventId": 69
}
```

### **cart_view**

```jsx
{
    "event": "view_cart",
    "ecommerce": {
        "currency": "INR",
        "value": 748,
        "items": [
            {
                "cart_url": {cart URL}
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "current_subtotal": {current cart total}
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "item_quantity": {Product Qnt Added} // TBA
            },
            {
                "cart_url": {cart URL}
                "item_id": {product Id},
                "item_name": {Product Name},
                "item_url": {Product URL},
                "item_image_url": {Product Image URL},
                "item_price": {Product price final},
                "item_sku": {Product Sku},
					      "item_compare_at_price": {Product original price}, // TBA
                "item_Variant": {product Variant Name}, // TBA
                "item_Variant_id": {product Variant Id}, // TBA
                "item_category": {product Category}, // TBA
                "item_quantity": {Product Qnt Added} // TBA
            }, 
            // more products if exist
        ]
    },
    "gtm.uniqueEventId": 29
}
```

### **thank_you_page**

```jsx
{
    "event": "thank_you_page",  
    "gtm.uniqueEventId": 69
}
```

### **form_submit**

```jsx

```

### **Identify Event**

Ideally, you should make the `identify` call in the following scenarios:

- After a user registers on your website or app
- After a user logs in to your site or app
- When a user updates their information, e.g., residential address, email ID
- when a user submits a form
- When you load a page accessible by a logged-in user: Although this is optional, many tools (such as Intercom, for example) require an initial identify call to know who the user is when they first start the session.

Sign Up

```jsx
{
    "event": "Signup Completed", 
    "ecommerce": {
            "SignupCompleted": {
               "identifiers":
											    {
											    "customer_id": {Customer ID},
											    "email": {Customer Email},
											    "phone": {Customer Phone}
											    }
                "customer_name": {Customer Name FULL}, 
						    "customer_first_name": {Customer First Name},
						    "customer_last_name": {Customer Last Name},
						    "address":
										    {
										        "city": {Customer City},
										        "country": {Customer Country},
										        "postalCode": {Customer postalCode},
										        "state": {Customer State},
										        "street": {Customer Street}
										    },
						    "age": {Customer Age "23"},
						    "birthday": {Customer Birthday "11/11/2002"},
						    "company":
										    {
										        "name": {Customer Company Name},
										        "id": {Customer Company ID},
										        "industry": {Customer Company industry},
										        "employee_count": {Customer Company Employee count},
										        "plan": {Customer Company plan}
										    },
						    "description": {Customer description Eg-"Tall"},
						    "gender": {Customer gender "Male"},
						    "title": {Customer title "Product Intern"},
						    "username": {Customer username "RishiZen"},
						    "website": {Customer website "www.google.com"},
						    "Avatar": {Customer Avatar url "www.pathToImage.com"} 
                
            }
    },
    "gtm.uniqueEventId": 45
}
```

Login 

```jsx
{
    "event": "Login Completed",
    "ecommerce": {
            "loginCompleted": {
               "identifiers":
											    {
											    "customer_id": {Customer ID},
											    "email": {Customer Email},
											    "phone": {Customer Phone}
											    }
                "customer_name": {Customer Name FULL}, 
						    "customer_first_name": {Customer First Name},
						    "customer_last_name": {Customer Last Name},
						    "address":
										    {
										        "city": {Customer City},
										        "country": {Customer Country},
										        "postalCode": {Customer postalCode},
										        "state": {Customer State},
										        "street": {Customer Street}
										    },
						    "age": {Customer Age "23"},
						    "birthday": {Customer Birthday "11/11/2002"},
						    "company":
										    {
										        "name": {Customer Company Name},
										        "id": {Customer Company ID},
										        "industry": {Customer Company industry},
										        "employee_count": {Customer Company Employee count},
										        "plan": {Customer Company plan}
										    },
						    "description": {Customer description Eg-"Tall"},
						    "gender": {Customer gender "Male"},
						    "title": {Customer title "Product Intern"},
						    "username": {Customer username "RishiZen"},
						    "website": {Customer website "www.google.com"},
						    "Avatar": {Customer Avatar url "www.pathToImage.com"}, 
                "user_type": {Customer type Eg)"Member"} // TBA
                
            }
    },
    "gtm.uniqueEventId": 45
}
```

**Note: At least 1 of the identifiers `{customer_id, email or phone}` must be passed in the Identify call.**