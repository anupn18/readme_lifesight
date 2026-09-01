---
title: '[4.0][WIP] RTB House'
excerpt: >-
  Connect RTB House to bring personalised retargeting spend into your unified
  measurement.
hidden: true
---
RTB House is a demand side platform specialising in personalised retargeting and brand awareness campaigns using deep learning bidding. Its campaigns typically run alongside your other display and programmatic activity, and they are frequently over credited by last click reporting because retargeting reaches people who were already close to buying.

That is precisely the reason to measure it properly rather than trust the platform's own conversion count.

## What Lifesight brings in

Lifesight reads the account hierarchy:

- **Advertiser** the top level account
- **Campaign** where objective, budget and flight dates are defined
- **Creative** the individual units served

The data pulled includes:

| Category | Data points |
| --- | --- |
| Performance metrics | Spend, Impressions, Clicks, Click Through Rate |
| Conversion metrics | Conversions, Conversion Value, Return on Ad Spend |
| Cost metrics | Cost Per Click, Cost Per Mille |
| Hierarchy dimensions | Advertiser, Campaign Name, Creative Name |

## Before you start

You need RTB House account credentials with access to the advertiser accounts you want to sync. If you are unsure whether your login has reporting access, your RTB House account manager can confirm it.

## Connecting RTB House

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for **RTB House** and click **Connect** on the tile.
3. On the **Authenticate** step, click **Sign in**.

![The RTB House authentication step](https://files.readme.io/a376fc4bb6d8b7df7e417a0fe95858be1a629234d244bd3004d3a9c7d3ea2539-connect-rtb-house-step1.png)

4. Sign in with your RTB House credentials and approve the access requested. Lifesight requests read access to reporting data only.
5. On the **Select Accounts** step, tick the advertiser accounts you want to sync.

![Selecting which RTB House accounts to sync](https://files.readme.io/7087b98d0b7cc99210eacc6fd8953cc4ee0e774f3545e31c18ce43c78489718a-connect-rtb-house-accounts.png)

6. Click **Connect**.

## After connecting

Check the field mappings in **Data > Data Transformation**, then classify the campaigns in **Data > Data Taxonomy**.

Give RTB House retargeting its own tactic rather than merging it into a general programmatic bucket. Retargeting and prospecting behave so differently that combining them produces an average that describes neither.

## Troubleshooting

**No advertiser accounts appear.** The credentials you used do not have reporting access. Contact your RTB House account manager to confirm access is enabled.

**Reported ROAS is much higher than what the model shows.** This is expected and is the reason for modelling. RTB House reports conversions it touched, many of which would have happened anyway. A model estimates the incremental portion, which is a different and more useful number.

**The integration went to Reconnect.** Authorisation expired or was revoked. Open the integration and sign in again.