---
title: '[4.0][Updated] Google Ads'
excerpt: >-
  Connect your Google Ads accounts to measure search, shopping, video and
  Performance Max spend alongside every other channel in Lifesight.
hidden: true
metadata:
  title: Lifesight X Google Ads
  keywords:
    - Lifesight
    - Google Ads
---
Google Ads reaches people at the moment they are looking for something, across Search, Shopping, YouTube, Display and Performance Max. For most advertisers it is both the largest line in the budget and the hardest to read honestly, because brand search takes credit for demand that already existed while prospecting campaigns do the work of creating it.

Connecting Google Ads gives Lifesight the campaign level detail needed to separate those two, rather than treating Google as one undifferentiated block of spend.

## What Lifesight brings in

Lifesight reads the full account hierarchy so that spend can be attributed at the level you actually manage it:

- **Account -** the ad account, useful when you run several campaigns.
- **Campaign -** where objective, budget and bidding live.
- **Ad Group -** targeting and keyword themes.
- **Ad -** the individual creative.

The data pulled includes:

| Category             | Data points                                                  |
| -------------------- | ------------------------------------------------------------ |
| Performance metrics  | Spend, Impressions, Clicks, Click Through Rate, Video Views  |
| Conversion metrics   | Conversions, Conversion Value, Attributed Revenue            |
| Cost metrics         | Cost Per Click, Cost Per Mille                               |
| Hierarchy dimensions | Account Name, Campaign Name, Ad Group Name, Ad Name          |
| Targeting dimensions | Country, Region, Device, Advertising Channel Type, Objective |

## Before you start

You need a Google account with access to the Google Ads accounts you want to sync. Read access is enough. If you manage clients through a manager account, sign in with the manager account and you will see everything underneath it in one go.

Worth confirming beforehand: which ad accounts actually carry the spend you want measured, and what currency each one reports in. Mixing currencies in a single model is a common and avoidable mistake.

## Connecting Google Ads

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for **Google Ads** and click **Connect** on the tile.
3. On the **Authenticate** step, click **Sign in**.

![The Google Ads authentication step](https://files.readme.io/f077baed5397463305be870811540ad5bf01b2f6cb19ed342eb03b62c53f6c99-connect-google-ads-step1.png)

4. You are taken to Google's sign in screen. Log in and approve the access Lifesight requests. Lifesight asks for read access to your reporting data. It never sees your password and cannot change campaigns through this connection.
5. Back in Lifesight, the **Select Accounts** step lists every Google Ads account your login can reach. Tick the ones you want to sync.

![Selecting which Google Ads accounts to sync](https://files.readme.io/038f8f57192f3fdea1e6f73a9a22006d990a1f2f2265980554d016ce946d49e7-connect-google-ads-accounts.png)

6. Click **Connect**.

Lifesight then starts its first pull, which covers your history and can take a while on a large account. The integration shows **Sync in Progress** until it is done, then **Healthy**.

## After connecting

Two things are worth doing straight away.

**Check the fields -** Open **Data > Data Transformation**, find Google Ads, and click **View Fields**. Most columns are mapped for you. Confirm that spend and your revenue field landed on the fields you expect.

![](https://files.readme.io/7aa8800357234e665fd6dbb6660b0f76a7f4b3e5a498c097071ddebd692d50f7-Screenshot_2026-09-01_at_5.02.46_PM.png)

<br />

**Classify the campaigns -** Open **Data > Data Taxonomy**. Google is where the brand and non-brand split matters most, so this is the highest value place to spend ten minutes. Sort by spend and work down.

***

## Troubleshooting

**Not all my accounts are listed&#x20;**<br />The Google login you used does not have access to them. Sign in with a manager account that covers them, or have someone grant your user access in Google Ads first.

**Spend does not match the Google Ads interface**<br />Check three things in order: the timezone the account reports in, whether every account is selected, and whether the date ranges truly match. Small differences are normal because platforms finalise numbers over several days.

**The integration went to Reconnect**<br />The Google account's authorisation expired or was revoked, which commonly happens when someone changes a password or leaves the company. Open the integration and sign in again. Nothing already synced is lost.

**Conversions look lower than in Google Ads**<br />Google reports conversions on its own attribution window and back-dates them to the click. That is a different question from the one Lifesight is answering, and a difference here is expected rather than a fault.

***

## Next up

Connect your:

- Microsoft Ads
- Snapchat Ads
- Reddit Ads