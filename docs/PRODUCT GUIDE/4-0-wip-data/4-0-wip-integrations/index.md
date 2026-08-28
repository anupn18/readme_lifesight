---
title: '[4.0][WIP] Integrations'
excerpt: >-
  Connect your ad platforms, files, and warehouses to Lifesight, and keep an eye
  on whether the data is still arriving.
hidden: false
---
An integration is a standing permission for Lifesight to read data from somewhere else on your behalf. You set it up once. After that Lifesight pulls fresh data on a schedule, so your reports and models keep up without anyone exporting a CSV every Monday.

This tab does two jobs. It is where you add new sources, and it is where you check that the ones you already added are still healthy.

![The Integrations tab listing connected sources with their status](https://files.readme.io/85c8e00f5f9ed1abf12c7963ef0224fd16faec6133a89a8c12812f9e1fe4e39c-integrations-list.png)

## The three kinds of source

When you click **Add Integration** you land on the catalogue, which is grouped into tabs.

**Native Integrations** are direct connections to a platform's API: Google Ads, Meta Ads, Snapchat Ads, Reddit Ads, Microsoft Ads, RTB House, StackAdapt and many more. These give you the richest data, because Lifesight reads the full campaign hierarchy rather than a flattened export. Most of them connect by signing in. A few use an API key you generate inside the platform.

**Files and Spreadsheets** cover the data that does not live in a platform: a CSV of offline sales, a Google Sheet where finance maintains cost of goods, an export from a system nobody has built a connector for yet. CSV uploads are one off or re-uploaded manually. Google Sheets stays linked and refreshes on a schedule.

**Data Warehouses** connect Lifesight to BigQuery or Snowflake and let you choose specific tables. Use this when your team has already done the modelling work and you want Lifesight to read the result rather than rebuild it.

**App Wishlist** is where you tell us about a platform we do not support yet. Requesting it registers a vote, and requests with the most demand get built first.

![The integration catalogue, grouped by type](https://files.readme.io/c29298424d6056060c786551407d23dbbab7fa21e688108dd939cc093e9870eb-integrations-catalog.png)

## Adding an integration

The exact steps depend on how the platform authenticates, but the shape is always the same.

### Platforms you sign in to

Most ad platforms use this flow. It has two steps.

1. Go to **Data > Integrations** and click **Add Integration**.
2. Search for the platform and click **Connect** on its tile.
3. On the **Authenticate** step, click **Sign in**. You are handed over to the platform's own login screen.

![The Authenticate step of the connection wizard](https://files.readme.io/7f2f1b7bdd9ddb368da1fba8a4775dec293d7fdecbd482ee4bdbf4744f2418cf-connect-step-authenticate.png)

4. Log in with an account that has access to the ad accounts you care about, and approve the permissions Lifesight asks for. Lifesight requests read access only. It never sees your password, and it cannot change your campaigns from this connection.
5. You are returned to Lifesight on the **Select Accounts** step, which lists every ad account your login can reach. Tick the ones you want to sync.

![The Select Accounts step, listing available ad accounts](https://files.readme.io/ff3c0741e15ce0c148b16ae62662d9609f83a3eb2dc3422651135148108edae8-connect-step-select-accounts.png)

6. Click **Connect** to finish.

A note on which accounts to select: pick the accounts whose spend you want measured, and leave out test accounts, dormant accounts, and accounts that report in a currency you are not modelling in. You can add or remove accounts later without redoing the sign in.

### Platforms that use an API key

Some platforms, StackAdapt among them, authenticate with a key you generate inside the platform rather than by signing in. The flow is the same except that step 3 asks you to paste the key instead of redirecting you. Each platform page in this section tells you exactly where to find its key.

### Files and spreadsheets

File based sources use a slightly different wizard, because there is no account to select and Lifesight has to work out what your columns mean.

1. **Name and Connect.** Give the source a name you will recognise later, and either upload the file or authorise access to the sheet.
2. **Data setup.** Lifesight previews the file and proposes what each column is. This is your chance to correct it before anything is imported.
3. **Schedule.** For linked sources such as Google Sheets, choose how often Lifesight should re-read it.

See [CSV Import](https://docs.lifesight.io/docs/4-0-wip-csv-import) and [Google Sheets](https://docs.lifesight.io/docs/4-0-wip-google-sheets) for the detail.

## Reading the integrations table

Once connected, each source becomes a row.

| Column | What it tells you |
| --- | --- |
| **Integration Name** | The platform, with its logo. Expand the row to see the individual accounts underneath. |
| **Status** | The health of the connection. See the table below. |
| **Integrated By** | Who set it up. Useful when a connection breaks and you need to know whose login it used. |
| **Data Sources** | How many accounts are syncing under this integration. |
| **Last Data Sync** | When fresh data last landed. If this is older than you expect, something has stalled. |

**View Details** opens the source, where you get three views: **Overview** for sync history and volume, **Context** for what this data is used for downstream, and **Configure** for changing accounts, schedule, and settings.

## What the statuses mean

| Status | What is happening | What to do |
| --- | --- | --- |
| **Healthy** | Data is arriving on schedule. | Nothing. |
| **Sync in Progress** | A pull is running right now. First syncs take longest because they cover your history. | Wait. Large accounts can take several hours. |
| **Transformation in Progress** | Data has arrived and is being shaped into Lifesight fields. | Wait. |
| **Sync Error** | Lifesight could not fetch data. Usually a platform side issue such as rate limiting or an API outage. | Lifesight retries automatically. If it persists, check the platform page. |
| **Transformation Error** | Data arrived but could not be processed. Usually a column changed shape. | Open Data Transformation for that source and check the field mappings. |
| **Reconnect** | Authorisation expired or was revoked. This happens when someone changes a password, leaves the company, or removes Lifesight's access at the platform. | Open the integration and sign in again. |
| **Unmapped** | Data is arriving but required fields are not mapped yet, so nothing downstream can use it. | Go to Data Transformation and map the mandatory fields. |
| **Paused** | Syncing is stopped on purpose. | Resume it when you want it back. |
| **Not Connected** | In the catalogue, not yet set up. | Connect it. |
| **Requested** | You asked for a connector that does not exist yet. | Nothing to do. We will let you know. |

## Managing an integration after setup

**Add or remove accounts.** Open the integration, go to Configure, and change the selection. Removing an account stops future syncs for it.

**Reconnect.** When a connection shows Reconnect, open it and sign in again with an account that still has access. You do not lose historical data by reconnecting.

**Pause.** Useful when you are troubleshooting or when a platform is mid migration and returning nonsense. Pausing keeps everything you already have.

**Remove.** Disconnects the source. Do this deliberately, because downstream models that depend on the source will be affected.

## Troubleshooting

**The accounts I expected are not in the list.** The login you used does not have access to them. Sign in with a different account, or ask whoever administers the ad account to grant your user access first.

**The integration connected but no data appeared.** Check the date range. Most platforms only expose data from the point the account started spending, and the first sync can take hours on a large account. If Last Data Sync is populated but numbers look empty, check Data Transformation to see whether the fields are mapped.

**Numbers do not match the platform's own dashboard.** This is common and usually explainable. Ad platforms report in the account's timezone and attribute conversions on their own window, so small differences are expected. Large differences usually mean a currency mismatch, a missing account, or a date range comparing different things.

**The status keeps flipping to Sync Error.** Check whether the account is rate limited or whether the platform has an incident. If it continues past a day, contact support with the integration name and the time the errors started.

## Platform guides

The pages below cover what each source provides, what you need before you start, and the exact steps for that platform.

- [Meta Ads](https://docs.lifesight.io/docs/4-0-wip-meta-ads)
- [Google Ads](https://docs.lifesight.io/docs/4-0-wip-google-ads)
- [Microsoft Ads](https://docs.lifesight.io/docs/4-0-wip-microsoft-ads)
- [Snapchat Ads](https://docs.lifesight.io/docs/4-0-wip-snapchat-ads)
- [Reddit Ads](https://docs.lifesight.io/docs/4-0-wip-reddit-ads)
- [RTB House](https://docs.lifesight.io/docs/4-0-wip-rtb-house)
- [StackAdapt](https://docs.lifesight.io/docs/4-0-wip-stackadapt)
- [CSV Import](https://docs.lifesight.io/docs/4-0-wip-csv-import)
- [Google Sheets](https://docs.lifesight.io/docs/4-0-wip-google-sheets)
