---
title: Shopify
excerpt: >-
  Brings your Shopify orders and revenue into Lifesight, so every model and test
  measures against the sales your store actually recorded.
deprecated: false
hidden: true
metadata:
  robots: noindex
---
Shopify is where your sales get recorded. For most ecommerce brands, it holds the number every model should explain: revenue that actually landed, not revenue an ad platform claims.

Connecting Shopify gives Lifesight the outcome side of measurement. Your ad platforms tell Lifesight what you spent. Shopify tells it what you sold. Marketing Mix Modeling, geo experiments and causal attribution all measure against it.

## What Lifesight brings in

Lifesight reads order data from your store and rolls it up to the daily level your models use.

| Data type           | Examples                                                       |
| ------------------- | -------------------------------------------------------------- |
| Sales metrics       | Orders, Gross Sales, Discounts, Returns, Net Sales, Total Sales |
| Customer metrics    | New Customers, Returning Customers                             |
| Order dimensions    | Order Date, Sales Channel, Currency                            |
| Location dimensions | Country, Region, City                                          |
| Product dimensions  | Product, Product Type, Vendor                                  |

Because every Shopify order carries a location, Lifesight can read sales by market. That is what geo experiments need to compare test and control regions.

## Before you start

You need:

- A Shopify login that can approve app permissions for the store. The store owner, or a staff account with app permissions, works.
- Permission to manage integrations in your Lifesight workspace.

If you run more than one store, for example one per region, connect each store separately.

## Connecting Shopify

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for **Shopify** and click **Connect** on the tile.
3. Enter or select the store you want to connect.
4. Sign in to Shopify and review the permissions Lifesight requests.
5. Approve the connection. Shopify returns you to Lifesight.

The first sync covers your order history and can take some time for larger stores. The status moves to **Healthy** once it is done.

<Callout icon="📘" theme="info">
  ### Setting up a new workspace?

  The Onboarding Agent asks you to connect Shopify in its second step, **Onboard your conversion data**. Connecting from that card and connecting from Integrations do the same thing.
</Callout>

## After connecting

Open **Data > Data Transformation**, find Shopify, and check the field mappings. Pay attention to which revenue field you use. Gross Sales, Net Sales and Total Sales answer different questions. Pick the one you want your model to explain, and use it the same way everywhere.

Then open **Model Schema**. For most ecommerce brands, Shopify revenue is the **Primary KPI**. See [Build a schema for Marketing Mix Modelling](https://docs.lifesight.io/docs/schema-mmm) for a worked example.

***

## Troubleshooting

**I can't approve the permissions**<br />Your Shopify user does not have app permissions. Ask the store owner to grant them, or to complete the connection for you.

**Revenue differs from Shopify Analytics**<br />Check four things: which revenue field is mapped (gross, net or total), how returns are counted, the store time zone, and the currency. Most gaps come from one of these, not from missing data.

**Recent days keep changing**<br />Returns, refunds and order edits update past orders. The last few days settle as those come in.

**The integration went to Reconnect**<br />This happens when the app is removed from the store or its permissions change. Open the integration and connect again.

**Some sales are missing**<br />Check that every store is connected. Sales from other systems, such as retail stores or marketplaces, need their own source. Use [CSV Import](https://docs.lifesight.io/docs/csv-import) or [Google Sheets](https://docs.lifesight.io/docs/google-sheets) to bring them in.

***

## FAQs

**Does Lifesight change anything in my store?**<br />No. Lifesight reads your order data. It does not edit orders, products or prices.

**Should my model use Shopify revenue or ad platform conversions?**<br />Shopify revenue, in most cases. Ad platforms each claim conversions on their own attribution windows, and those claims overlap. Shopify records each sale once, so it is the right number for a model to explain.

**Can I connect more than one store?**<br />Yes. Connect each store separately. You can then keep them apart or combine them in Data Transformation.

**How do I include offline or marketplace sales?**<br />Bring them in as their own source with CSV Import or Google Sheets. [Set a fixed value for a source](https://docs.lifesight.io/docs/fixed-value-source) shows how to line up sources that are missing a field, such as country.

**How often does the data refresh?**<br />Lifesight syncs Shopify automatically after the first connection. You can see the latest sync time on the integration in **Data > Integrations**.

***

## Next up

Connect your:

- [Meta Ads](https://docs.lifesight.io/docs/meta-ads)
- [Google Ads](https://docs.lifesight.io/docs/google-ads)
- [Google Sheets](https://docs.lifesight.io/docs/google-sheets)
