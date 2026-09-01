---
title: '[4.0][Updated] Reddit Ads'
excerpt: >-
  Connect Reddit Ads to see what community-driven advertising actually returns,
  and whether it earns a larger share of budget.
hidden: true
---
Reddit advertising reaches people inside communities organised around genuine interest, which makes it useful for categories where people research carefully before buying. The Reddit Ads API lets Lifesight pull campaign and account data programmatically, so you get reporting without anyone opening Reddit Ads Manager to export it.

## What Lifesight brings in

Lifesight reads the Reddit hierarchy:

- **Campaign** the highest level, where the objective is set
- **Ad Group** where targeting, budget and scheduling live
- **Ad** the individual creative

The data pulled includes:

| Category | Data points |
| --- | --- |
| Performance metrics | Spend, Impressions, Clicks, Click Through Rate, Video Views |
| Conversion metrics | Sign Ups, Add to Carts, Purchases, Page Visits, Custom Conversions |
| Cost metrics | Cost Per Click, Cost Per Mille |
| Hierarchy dimensions | Campaign Name, Ad Group Name, Ad ID, Ad Name |

## Before you start

You need a Reddit Ads account and login credentials with access to the ad accounts you want to sync.

## Connecting Reddit Ads

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for **Reddit Ads** and click **Connect** on the tile.
3. On the **Authenticate** step, click **Sign in**.

![The Reddit Ads authentication step](https://files.readme.io/592c34e9ba9b534db62e9b529ed922207fac0d2536d8888ebcb87bf1f6598891-connect-reddit-ads-step1.png)

4. You are taken to Reddit's authentication screen. Log in with your Reddit Ads credentials.
5. Review the permissions screen, which details the data Lifesight will access, and approve it.
6. Back in Lifesight, select one or more ad account IDs you want to pull data from.

![Selecting which Reddit ad accounts to sync](https://files.readme.io/d34b84de2412590e178289b950d7fc7fca16e0e0dd604159ca8b99efaaeac438-connect-reddit-ads-accounts.png)

7. Click **Connect** to finish.

Lifesight begins its initial data pull. Depending on how much history you have, this can take some time.

## After connecting

Check the mappings in **Data > Data Transformation**, then classify the campaigns in **Data > Data Taxonomy**.

Reddit sits somewhere between social and search in how it behaves, so it is worth giving it its own tactic rather than folding it into a generic paid social bucket. That way the model estimates it on its own evidence.

## Troubleshooting

**No ad accounts appear after signing in.** The Reddit user you authenticated with does not have access to an ad account. Check permissions in Reddit Ads Manager.

**Conversion numbers look sparse.** Reddit conversion tracking depends on the Reddit Pixel or Conversions API being correctly installed. If those are not set up, conversion columns will be thin, though spend, impressions and clicks will still be complete and are enough for modelling.

**The integration went to Reconnect.** Authorisation expired or was revoked. Open the integration and sign in again.