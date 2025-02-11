---
title: Custom Connector
excerpt: Connect any custom data sources using custom APIs and webhooks
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Custom connectors let you send and receive data using APIs and webhooks that are not supported in our catalog of [native destinations](https://docs.lifesight.io/docs/native-integrations#list-of-native-integrations).

<br />

## How to use custom APIs with Lifesight

1. Navigate to Connect > Integrations from the left-hand menu.
2. Search for "Custom Connector" to locate the integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42ec03eafc2177afeeda606124d2dc811912f8a263167d165b2a7114ec774a98-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]


> 🚧 Need help setting up a custom integration?
> 
> Lifesight marketing science services help you connect, ingest and transform your data from any sources using custom APIs and webhooks based on your requirement.

3. Name your integration and click "Begin Setup" (you can change the name while configuring your connector)
4. Click "+Create new" and choose if you want to set up a new API or new webhook. Select "new API" and click "Next".
5. Name your custom API and click Next.
6. In the connector dashboard, click on "Configure" to setup the custom API. Enter the API endpoint URL or import CURL, add any required headers, and include query parameters if necessary.

![](https://files.readme.io/737a62925a10c8987326bfb27d8647c2f48dc763cf965e6a3b663af5e5178658-image.png)

<br />

7. Map the response fields to the global fields available within Lifesight. This ensures that the data from your API requests seamlessly integrates into the platform.
8. To incorporate more data from the same or different sources, add additional API requests to your custom integration.
9. For each new API request, repeat the configuration and schema mapping process

***

<br />

## How to use custom webhooks

1. Navigate to Connect > Integrations from the left-hand menu.
2. Search for "Custom Connector" to locate the integration.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/42ec03eafc2177afeeda606124d2dc811912f8a263167d165b2a7114ec774a98-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "400px"
    }
  ]
}
[/block]


> 🚧 Need help setting up a custom integration?
> 
> Lifesight marketing science services help you connect, ingest and transform your data from any sources using custom APIs and webhooks based on your requirement.

3. Name your integration and click "Begin Setup" (you can change the name while configuring your connector)
4. Click "+Create new" and choose if you want to set up a new API or new webhook. Select "new webhook" and click "Next".
5. Name your custom API and click Next.
6. In the connector dashboard, click on "Configure" to setup the custom webhook. Copy and paste the JSON payload and click "Next".

![](https://files.readme.io/4bb3dd93509a1fcce29d51ed2db442e07c22df1d719df915ee9c6994dd2f1638-image.png)

<br />

7. Map the response fields to the global fields available within Lifesight. This ensures that the data from your webhook requests seamlessly integrates into the platform.
8. To incorporate more data from the same or different sources, add additional webhook requests to your custom integration.
9. For each new API request, repeat the configuration and schema mapping process.