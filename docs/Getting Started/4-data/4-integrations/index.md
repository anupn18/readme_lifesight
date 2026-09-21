---
title: '[4.0][Updated] Integrations'
excerpt: >-
  Connect your ad platforms, files, and warehouses to Lifesight, and keep an eye
  on whether the data is still populating..
hidden: true
metadata:
  title: Lifesight Integrations
  keywords:
    - Lifesight
    - Integrations
---
An integration is a standing permission for Lifesight to read data from another platform on your behalf. You connect the source once, and Lifesight refreshes it on a set schedule, so your reports and models stay updated with the latest data without anyone exporting a CSV every Monday.

Integrations serves two purposes: it is where you connect new data sources, and where you confirm that the sources you already connected are still syncing as expected.

![](https://files.readme.io/839d5610ce8c99cf2b8525e5ee0780a511a57225c841916a1314fd3bb55f7d86-Screenshot_2026-09-01_at_3.19.04_PM.png)

<br />

***

## Three Kind of Data Sources

When you click **Add Integration** you land on the catalogue, which is grouped into tabs.

**Native Integrations** are direct connections to a platform's API: Google Ads, Meta Ads, Snapchat Ads, Reddit Ads, Microsoft Ads, RTB House, StackAdapt and many more. These give you the richest data, because Lifesight reads the full campaign hierarchy rather than a flattened export. Most of them connect by signing in. A few use an API key you generate inside the platform.

**Files and Spreadsheets** cover the data that does not live in a platform: a CSV of offline sales, a Google Sheet where finance maintains cost of goods, an export from a system nobody has built a connector for yet. CSV uploads are one off or re-uploaded manually. Google Sheets stays linked and refreshes on a schedule.

**Data Warehouses** connect Lifesight to BigQuery or Snowflake and let you choose specific tables. Use this when your team has already done the modelling work and you want Lifesight to read the result rather than rebuild it.

**App Wishlist** is where you tell us about a platform we do not support yet. Requesting it registers a vote, and requests with the most demand get built first.

![](https://files.readme.io/6f24d91fda829475d15f4f3a0df8db9d59bb7548411e603a417dad2b5069377d-Screenshot_2026-09-01_at_3.20.03_PM.png)

## Adding an Integration

The exact steps depend on how the platform authenticates, but the mostly its always the same.

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

<Callout icon="📘" theme="info">
  Pick the accounts whose spend you want measured, and leave out test accounts, dormant accounts, and accounts that report in a currency you are not modelling in. You can add or remove accounts later without redoing the sign in.
</Callout>

***

### Platforms That Use an API Key

Some platforms, StackAdapt among them, authenticate with a key you generate inside the platform rather than by signing in. The flow is the same except that step 3 asks you to paste the key instead of redirecting you.&#x20;

Each platform page in this section tells you exactly where to find its key.

***

### Files and Spreadsheets

File based sources use a slightly different wizard, because there is no account to select and Lifesight has to work out what your columns mean.

1. **Name and Connect.** Give the source a name you will recognise later, and either upload the file or authorise access to the sheet.
2. **Data setup.** Lifesight previews the file and proposes what each column is. This is your chance to correct it before anything is imported.
3. **Schedule.** For linked sources such as Google Sheets, choose how often Lifesight should re-read it.

See [CSV Import](https://docs.lifesight.io/docs/4-0-wip-csv-import) and [Google Sheets](https://docs.lifesight.io/docs/4-0-wip-google-sheets) for more details.

***

## Reading the Integrations Table

Once connected, each source becomes a row.

| Column               | What it tells you                                                                        |
| -------------------- | ---------------------------------------------------------------------------------------- |
| **Integration Name** | The platform, with its logo. Expand the row to see the individual accounts underneath.   |
| **Status**           | The health of the connection. See the table below.                                       |
| **Integrated By**    | Who set it up. Useful when a connection breaks and you need to know whose login it used. |
| **Data Sources**     | How many accounts are syncing under this integration.                                    |
| **Last Data Sync**   | When fresh data last landed. If this is older than you expect, something has stalled.    |

**View Details** opens the source, which has three tabs.

![](https://files.readme.io/11ba54579213686dc81e064ac8c991d7357d077f66924ef26bc70ee4ad8dc715-Screenshot_2026-09-01_at_3.31.00_PM.png)

<br />

***

### Overview

What is actually arriving. A date range selector sits at the top, and under it the headline numbers this source has delivered over that window: **Spend**, **Impressions**, **Clicks** and **Attributed Revenue**, charted over time.

Open this tab(overview) first when a number looks wrong elsewhere in the platform, because it answers the question worth asking up front: is the data coming through, and does its shape look right. A flat line where there should be spend, or a sudden step change, usually points to a sync issue or an account that stopped being included.

If the source is connected and syncing but its fields have not been mapped yet, this tab will tell you so rather than show empty charts.That points you to [Data Transformation](https://docs.lifesight.io/docs/4-0-wip-data-transformation), and is not a fault with the connection.

![](https://files.readme.io/db92e0d8d9f302af7db9992eceaf795fe8609b0687526a069b8d04dfd242ebd3-Screenshot_2026-09-01_at_4.38.22_PM.png)

<br />

***

### Configure

The Configure tab is where you change how an integration behaves. It has three sections.

**Connection Details** is read-only reference: the date the source was connected, the refresh frequency, the timezone the data is reported in, and the connection type. Timezone is the one people overlook, and it explains most small discrepancies against a platform's own dashboard.

**Accounts lists** every account under this integration with a checkbox against each, and a count such as "5 of 5 selected". Selected accounts sync into Lifesight; deselect one to stop new data coming in from it. Accounts created after the integration was set up are flagged New, which is how you catch an ad account someone opened without telling you. None of these changes take effect until you apply them, so you can review the full selection before committing.

**Configuration holds the destructive action:** removing the integration and the data it brought in. Check the Context tab before you do.&#x20;

For CSV and Excel sources this tab also offers re-upload, which is how you refresh a file without creating a second integration and splitting its history.

![An integration's Configure tab](https://files.readme.io/e5263726212c9cff09c3dd19024bd805e232d6c3fa996e153d5d94c0d1173c9a-integration-detail-configure.png)

<br />

***

### Context (Coming Soon)

What this source is used for downstream. It answers the question people ask before touching anything: if I pause or remove this, what breaks.

Worth checking before you disconnect a source or deselect an account, because a source feeding a live model is not one to experiment with casually.

## What the Statuses Mean

| Status                         | What is happening                                                                                                                                      | What to do                                                                |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| **Healthy**                    | Data is arriving on schedule.                                                                                                                          | Nothing.                                                                  |
| **Sync in Progress**           | A pull is running right now. First syncs take longest because they cover your history.                                                                 | Wait. Large accounts can take several hours.                              |
| **Transformation in Progress** | Data is in the platform and is being shaped into Lifesight fields.                                                                                     | Wait for dats to populate.                                                |
| **Sync Error**                 | Lifesight could not fetch data. Usually a platform side issue such as rate limiting or an API outage.                                                  | Lifesight retries automatically. If it persists, check the platform page. |
| **Transformation Error**       | Data arrived but could not be processed. Usually a column changed shape.                                                                               | Open Data Transformation for that source and check the field mappings.    |
| **Reconnect**                  | Authorisation expired or was revoked. This happens when someone changes a password, leaves the company, or removes Lifesight's access at the platform. | Open the integration and sign in again.                                   |
| **Unmapped**                   | Data is arriving but required fields are not mapped yet, so nothing downstream can use it.                                                             | Go to Data Transformation and map the mandatory fields.                   |
| **Paused**                     | Syncing is stopped on purpose.                                                                                                                         | Resume it when you want it back.                                          |
| **Not Connected**              | In the catalogue, not yet set up.                                                                                                                      | Connect it.                                                               |
| **Requested**                  | You asked for a connector that does not exist yet.                                                                                                     | Nothing to do. We will let you know.                                      |

## Managing an Integration After Setup

**Add or remove accounts.** Open the integration, go to Configure, and change the selection. Removing an account stops future syncs for it.

**Reconnect.** When a connection shows Reconnect, open it and sign in again with an account that still has access. You do not lose historical data by reconnecting.

**Pause.** Useful when you are troubleshooting or when a platform is mid migration and returning nonsense. Pausing keeps everything you already have.

**Remove.** Disconnects the source. Do this deliberately, because downstream models that depend on the source will be affected.

***

## Troubleshooting

**The integration connected but no data appeared**

Check the date range. Most platforms only expose data from the point the account started spending, and the first sync can take hours on a large account. If Last Data Sync is populated but the numbers look empty, check Data Transformation to see whether the fields are mapped.

**Numbers do not match the platform's own dashboard**

This is common and usually explainable. Ad platforms report in the account's timezone and attribute conversions on their own window, so small differences are expected. Large differences usually point to a currency mismatch, a missing account, or a date range comparing different periods.

**The accounts I expected are not in the list**

The login you used does not have access to them. Sign in with a different account, or ask whoever administers the ad account to grant your user access first.

**The status keeps flipping to Sync Error**

Check whether the account is rate limited or whether the platform has an incident. If it continues past a day, contact support with the integration name and the time the errors started.

***

## Next up

### Platform guides

The pages below cover what each source provides, what you need before you start, and the exact steps for that platform.

- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-meta-ads">Meta Ads</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-google-ads">Google Ads</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-microsoft-ads">Microsoft Ads</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-snapchat-ads">Snapchat Ads</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-reddit-ads">Reddit Ads</Anchor>
- [RTB House](https://docs.lifesight.io/docs/4-0-wip-rtb-house)
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-stackadapt">StackAdapt</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-csv-import">CSV Import</Anchor>
- <Anchor target="_blank" href="https://docs.lifesight.io/docs/4-0-wip-google-sheets">Google Sheets</Anchor>