---
title: '[4.0][Updated] Snapchat Ads'
excerpt: >-
  Connect Snapchat Ads to see what vertical video and AR spend returns, and
  decide whether it deserves more budget.
hidden: true
metadata:
  title: Lifesight X Snapchat
  keywords:
    - Lifesight
    - Snapchat
---
Snapchat reaches a predominantly Gen Z and Millennial audience through mobile first vertical video and augmented reality formats. It tends to drive attention and brand engagement rather than a click that closes immediately, which makes it exactly the sort of channel that looks weak in last click reporting and considerably stronger in a properly specified model.

Connecting Snapchat means its contribution gets measured rather than assumed.

<Callout icon="📘" theme="info">
  **Work in progress.** In the 4.0 build this connector is not yet selectable from the **Add Integration** catalogue. The steps below describe the connection flow it will use, and match how Snapchat Ads works in the current production release.
</Callout>

## What Lifesight brings in

Lifesight reads the Snapchat hierarchy:

- **Ad Account** the account holding the spend
- **Campaign** where the objective is set
- **Ad Squad** where audience, budget and schedule live
- **Ad** the individual creative

The data pulled includes:

| Category             | Data points                                                    |
| -------------------- | -------------------------------------------------------------- |
| Performance metrics  | Spend, Impressions, Swipe Ups, Click Through Rate, Video Views |
| Conversion metrics   | Purchases, Add to Cart, Sign Ups, Conversion Value             |
| Cost metrics         | Cost Per Click, Cost Per Mille                                 |
| Hierarchy dimensions | Account Name, Campaign Name, Ad Squad Name, Ad Name            |
| Targeting dimensions | Country, Region, Device, Objective                             |

## Before you start

You need a Snapchat account with access to the Snapchat Ads accounts you want to sync, granted through Snapchat Business Manager. Read access is enough.

## Connecting Snapchat Ads

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for **Snapchat** and click **Connect** on the tile.
3. On the **Authenticate** step, click **Sign in**.
4. Log in with your Snapchat credentials and approve the access requested.
5. On the **Select Accounts** step, tick the ad accounts you want to sync.
6. Click **Connect**.

## After connecting

Check the field mappings in **Data > Data Transformation**, then classify the campaigns in **Data > Data Taxonomy**.

Snapchat is usually best treated as an upper funnel tactic. If you classify it alongside your other video and awareness activity rather than lumping it in with performance channels, the model can estimate the effect of that whole tier of spend rather than trying to explain one small platform on its own.

***

## Troubleshooting

**Ad accounts are not listed.** Your Snapchat user has not been granted access in Business Manager. Ask the admin to add you, then sign in again.

**Swipe ups look low compared to clicks elsewhere.** That is a real difference in user behaviour and format rather than a data problem. It is one of the reasons click based comparison across platforms is misleading and modelled comparison is not.

**The integration went to Reconnect.** Authorisation expired or was revoked. Open the integration and sign in again.
