---
title: Snowflake
excerpt: >-
  Connect Snowflake to bring any data stored in your warehouse into Lifesight,
  from paid and organic performance to KPIs and contextual factors.
deprecated: false
hidden: true
metadata:
  robots: index
---
If your data is already stored in Snowflake, there is no reason to export it. That covers paid media, organic activity, KPIs such as revenue and orders, and contextual factors such as pricing and promotions.

Lifesight only reads your data. It never writes, changes or deletes anything in Snowflake.

Setup has three steps. You do the first two once, and the third for each table you want to bring in.

## Before you start

Have these ready:

* **A Snowflake admin.** Someone who can run a script as `ACCOUNTADMIN`.
* **Your account identifier.** The part of your Snowflake URL before `.snowflakecomputing.com`, for example `acme-xy12345`.
* **A warehouse name.** An X-Small warehouse is enough.
* **The database, schema and table names** you want to bring in.

You do not need to create a user or share a password. Lifesight signs in with a secure key pair, and nothing secret is typed or pasted.

## Step 1: Add your Snowflake credential

A credential is the saved sign-in to your Snowflake account. You add it once and reuse it for every table.

1. Go to **Data > Integrations** and click **Add Integration**.
2. Open the **Data Warehouses** tab and click **Connect** on Snowflake.

![The Data Warehouses tab of Add Integration, showing Snowflake](https://files.readme.io/cc2e92e4b1dbc937ce23613539d04f9d4b0a7f104bd155f1e28e254b8934d0ca-snowflake-add-integration.jpg)

3. Click **Add credential**.
4. Fill in the four fields.

| Field | What to enter | Example |
| :-- | :-- | :-- |
| Credential name | Any name that helps you recognise this sign-in. | `Acme analytics` |
| Account identifier | The part of your Snowflake URL before `.snowflakecomputing.com`. Not the full URL. | `acme-xy12345` |
| Warehouse | The warehouse name only. | `LIFESIGHT_WH` |
| Databases and schemas | Every database and schema you plan to read. Click **Add database** to add more. | `ANALYTICS` with `MARKETING`, `FINANCE` |

![The Add Snowflake credential dialog with its fields filled in](https://files.readme.io/ab071ae62d8e791cf5293e0204878c9dacba9488094db632c2d214dbc773cfd7-snowflake-add-credential.jpg)

> 📘 Enter names on their own
>
> Type `ANALYTICS` as the database and `MARKETING` as the schema, not `ANALYTICS.MARKETING`. If a name has spaces or lowercase letters, wrap it in double quotes.

## Step 2: Run the setup script

The setup script creates a read-only user for Lifesight in your Snowflake account and gives it access to the data you listed. It is already filled in with what you typed in step 1.

1. Under **Grant read on**, choose **One table** and type the table name, or choose **All tables** to include every table in the schemas you listed.
2. Click **Copy**.
3. In Snowflake, paste the script into a worksheet and run all of it as `ACCOUNTADMIN`.
4. Back in Lifesight, click **Test and save**.

![The Setup script section of the credential dialog, with the Copy button](https://files.readme.io/289ba4e2c5df2a6b57a88e3d12e0303d95c86376f2df6003418ae812b6dbadc9-snowflake-setup-script.jpg)

When the test passes, the credential is saved and marked **Access verified**.

The script is safe to run again. Re-run it whenever you add a database, schema or table.

> 📘 Does your Snowflake account restrict sign-in by IP?
>
> Allow Lifesight's IP address `35.206.86.230`. Open **Firewall** in the same dialog, copy the script, and run it in Snowflake.

## Step 3: Connect a table

Each Snowflake integration brings in one table. Repeat this step for every table, using the same credential.

### Name and connect

Enter an **Integration Name**, pick your **Credential**, choose the **Database** and **Schema**, then click **Verify and continue**.

![Step 1 of the wizard with a credential, database and schema selected](https://files.readme.io/5a04e43f580557c3977b37a6190b82fff36f2c0909844d5883cb00575e06386c-snowflake-name-and-connect.jpg)

### Select a table

Pick the table you want to bring in. Its columns show on the right. Then click **Continue**.

![Step 2 of the wizard with a table selected and its columns listed](https://files.readme.io/07ef82670b5e30a9ee2fcfe3598c3d6b25c3991ba42b59fd70e05447958e8432-snowflake-select-table.jpg)

* Only tables and materialized views are listed.
* A table that is already connected is greyed out, so it is never counted twice.

### Data setup

Check the preview, then confirm two things: which column holds the date, and whether your data is laid out as **Stacked rows** or **Pivoted columns**.

![Step 3 of the wizard with the date column and layout choices](https://files.readme.io/b3aea3e746640e1d78388588e58ce75ee388d522db0720ca9b6c5bedaff1c729-snowflake-data-setup.jpg)

### Schedule and sync

Choose how often Lifesight should refresh the data: **Daily**, **Weekly**, **Monthly** or **Manual**.

![Step 4 of the wizard with the refresh frequency and time](https://files.readme.io/88c90c2203a84e07f07366eafc515d47c6fcddc7c17eb9dbe8398a69f2a89d48-snowflake-schedule.jpg)

Then choose what happens on each refresh:

| Option | What it does | Use it when |
| :-- | :-- | :-- |
| Replace and append (recommended) | Updates matching rows, adds new rows and keeps the rest. | Your table grows over time. |
| Full replace | Replaces everything with the latest copy of the table. | Your table is always the complete, current picture. |

Click **Connect**. The first sync starts straight away and can take 24 to 48 hours to complete.

## What happens next

* Your Snowflake integration appears on **Data > Integrations** with its status and last sync time.
* Open **Data > Data Transformation** to map the table's columns to Lifesight fields.
* To bring in another table, repeat step 3 with the same credential.

## Changing a credential

On the first step of the wizard, pick the credential and click **Edit**.

* You can change its name, warehouse, and databases and schemas. After adding a database or schema, re-run the setup script and click **Test and save**.
* You cannot change the account identifier once an integration uses the credential. Add a new credential instead.
* If you remove a database or schema that an integration reads, that integration stops refreshing. Lifesight warns you before you save, and data already loaded stays.

## Troubleshooting

| What you see | What to do |
| :-- | :-- |
| "We could not sign in to your account" | Make sure the whole setup script was run as `ACCOUNTADMIN`, wait a minute, then click **Test and save** again. |
| "Lifesight cannot read database" or "schema" | Check the name is spelled exactly as in Snowflake, re-run the setup script, then test again. |
| "Enter only the part before .snowflakecomputing.com" | Enter only the account identifier, for example `acme-xy12345`, not the full URL. |
| "JWT token is invalid" in Snowflake | Copy the script again from Lifesight and run it without editing the key. |
| A table is missing from the list | Check that it is a table or materialized view, and that its schema is listed on the credential. |
| Sign-in fails and your account uses a network policy | Allow Lifesight's IP `35.206.86.230` using the **Firewall** script. |

Still stuck? Contact Lifesight support and include the message you see.