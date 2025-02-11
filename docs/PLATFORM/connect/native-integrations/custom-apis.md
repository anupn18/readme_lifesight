---
title: Custom APIs
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
An Application Programming Interface (API) is a crucial technological framework that establishes protocols, rules, and tools for building software and applications. It allows different software applications to communicate with each other, thereby enabling the exchange of data, features, and functionalities seamlessly. 

A simple way to understand how APIs work is to look at a common example—third-party payment processing. When a user purchases a product on an e-commerce site, they may be prompted to “Pay with Paypal” or another type of third-party system. This function relies on APIs to make the connection.When the buyer clicks the payment button, an API calls to retrieve information—also known as a request.

This request is processed from an application to the web server through the API’s Uniform Resource Identifier (URI) and includes a request verb, headers, and sometimes, a request body.After receiving a valid request from the product webpage, the API makes a call to the external program or web server, in this case, the third-party payment system.The server sends a response to the API with the requested information.The API transfers the data to the initial requesting application, here the product website.

<br />

## Implementing Custom API

1. Navigate to the Integrations tab in the left-hand menu bar.
2. In the search field, type in "CustomAPI" to locate the integration.
3. Click on the Custom API tile and begin by naming your custom integration. This name will also serve as the schema name, making it easier to identify and reference in the future
4. Click on Configure to begin inputting the API endpoint, add any required headers, and include query parameters if necessary.
5. Map the response fields to the global fields available within Lifesight. This ensures that the data from your API requests seamlessly integrates into the platform.
6. To incorporate more data from the same or different sources, add additional API requests to your custom integration.
7. For each new API request, repeat the configuration and schema mapping process 

<br />

Once all API requests are correctly configured and mapped, finalize the setup process.
