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
Snowflake is the cloud data warehouse where many teams keep the data that does not live in an ad platform: revenue and orders, organic and CRM activity, pricing, promotions, and spend from channels with no connector of their own.

Connecting Snowflake lets Lifesight read those tables on a schedule, so nobody has to export and upload files.

**On this page**

1. [What Lifesight brings in](#what-lifesight-brings-in)
2. [Before you start](#before-you-start): what to have ready
3. [Set up the Snowflake credential](#creating-a-snowflake-user-for-lifesight): done once, usually by your data or IT team
   * [Step 1: Create the two key files](#step-1-create-the-two-key-files)
   * [Step 2: Create the user in Snowflake](#step-2-create-the-user-in-snowflake)
   * [Step 3: Copy the private key and keep it safe](#step-3-copy-the-private-key-and-keep-it-safe)
4. [Connect Snowflake](#connecting-snowflake): done in Lifesight, once per table
   * [Name and connect](#1-name-and-connect)
   * [Select a table](#2-select-a-table)
   * [Data setup](#3-data-setup)
   * [Schedule and sync](#4-schedule-and-sync)
5. [After connecting](#after-connecting): map your fields
6. [Troubleshooting](#troubleshooting)

***

## What Lifesight brings in

* **Only the tables you choose.** Tables and materialized views in the databases and schemas you give access to.
* **One table per integration.** Add an integration for each table and reuse the same credential.
* **Read only.** Lifesight never writes to, changes or deletes anything in Snowflake.

You tell Lifesight what kind of data each table holds when you connect it:

| Kind of data | Examples |
| :-- | :-- |
| Paid Marketing | Spend, impressions and clicks from channels without a native connector |
| KPI | Revenue, orders, leads, sign-ups |
| Organic | Email sends, organic social, search visibility |
| Contextual | Pricing, promotions, seasonality, stock levels |

***

## Before you start

You need:

1. **A Snowflake admin**, to create a user for Lifesight. This can be you or your data or IT team.
2. **Your account identifier.** The part of your Snowflake URL before `.snowflakecomputing.com`. In `acme-xy12345.snowflakecomputing.com`, it is `acme-xy12345`.
3. **The names of what Lifesight should read:**
   * the warehouse (an X-Small warehouse is enough)
   * the databases and schemas
   * the tables

### Creating a Snowflake user for Lifesight

Lifesight signs in to Snowflake as its own read-only user, with a key pair instead of a password.

> 👍 You do not have to do this yourself
>
> Send this section to whoever looks after Snowflake at your company. It takes about ten minutes. They send you back the private key file and the names you need for the form.

#### Step 1: Create the two key files

1. Open a terminal:
   * **Mac:** press `Cmd + Space`, type `Terminal` and press Enter.
   * **Windows:** use **Git Bash**, or ask your IT team to run this step.
2. Paste the two lines below and press Enter.

```bash
openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

3. Check that two new files are in your home folder:

| File | What it is | Where it goes |
| :-- | :-- | :-- |
| `rsa_key.pub` | The public key. Not secret. | On the Snowflake user, in step 2. |
| `rsa_key.p8` | The private key. Keep it secret. | Into Lifesight, when you add the credential. |

Both are plain text files. The public key looks like this. The private key looks the same, but is longer and says `PRIVATE KEY`.

```text
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAu7Tq9xw2LkP4vGm1Zc8H
Rn3JfQyE6bWdS0aKtNvXo5Ll2pMhCzYs9gUeI1AjB7rFxD4kVtq8ZnWmPc3oRbLy
... a few more lines like these ...
8QIDAQAB
-----END PUBLIC KEY-----
```

#### Step 2: Create the user in Snowflake

1. Print the public key as one line, the form Snowflake needs. Run this, then select the output and copy it.

```bash
grep -v "PUBLIC KEY" rsa_key.pub | tr -d '\n'
```

2. In Snowflake, click **+** and open a new **SQL Worksheet**.
3. Paste the script below and replace each placeholder:
   * `<WAREHOUSE_NAME>`: your warehouse
   * `<DATABASE_NAME>` and `<SCHEMA_NAME>`: where your data is
   * `<TABLE_NAME>`: the table to share
   * `<PUBLIC_KEY>`: the line you copied, inside the quotes
4. Choose the read access in step 6 of the script:
   * **Option A (recommended):** only the tables you name, one line each. This is all Lifesight needs.
   * **Option B:** every table in the schema, including ones created later. Use it if new tables appear regularly.
5. Run the whole script as `ACCOUNTADMIN`. It is safe to run again later.

```sql
-- ============================================================================
-- LIFESIGHT: SNOWFLAKE SETUP
-- ============================================================================
-- Creates a read-only service user that Lifesight signs in as. Sign-in is by
-- key pair only: no password is created or stored.
--
-- BEFORE YOU RUN
--   1. Replace every <PLACEHOLDER> with your own value.
--   2. Run the whole script in a worksheet as ACCOUNTADMIN.
--   3. It is safe to run again. It never removes existing grants.
-- ============================================================================

-- STEP 1: Create the service user
USE ROLE USERADMIN;

CREATE USER IF NOT EXISTS LIFESIGHT
  LOGIN_NAME   = 'LIFESIGHT'
  DISPLAY_NAME = 'Lifesight Integration'
  COMMENT      = 'Read-only service user for the Lifesight integration';

-- STEP 2: Key-pair sign-in, user type and default warehouse
-- These run every time, so they also apply if the user already existed.
ALTER USER LIFESIGHT UNSET PASSWORD;
ALTER USER LIFESIGHT SET TYPE = SERVICE;
ALTER USER LIFESIGHT SET
  DEFAULT_WAREHOUSE = <WAREHOUSE_NAME>
  RSA_PUBLIC_KEY    = '<PUBLIC_KEY>';
-- ^ The public key as one line, without the BEGIN/END lines or line breaks.

-- STEP 3: Create the read-only role and give it to the user
USE ROLE SECURITYADMIN;

CREATE ROLE IF NOT EXISTS LIFESIGHT_READER;
GRANT ROLE LIFESIGHT_READER TO USER LIFESIGHT;
ALTER USER LIFESIGHT SET DEFAULT_ROLE = LIFESIGHT_READER;

-- STEP 4: Let the role use the warehouse
GRANT USAGE ON WAREHOUSE <WAREHOUSE_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 5: Let the role see the database and schema (this gives no data access)
-- Repeat the SCHEMA line for each extra schema.
GRANT USAGE ON DATABASE <DATABASE_NAME>               TO ROLE LIFESIGHT_READER;
GRANT USAGE ON SCHEMA   <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 6: Give read access to your data. Choose ONE option.
-- Lifesight only needs SELECT on the tables you want to sync.

-- OPTION A (recommended): only the tables you list. One line per table.
GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME_2> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON MATERIALIZED VIEW <DATABASE_NAME>.<SCHEMA_NAME>.<VIEW_NAME> TO ROLE LIFESIGHT_READER;

-- OPTION B (broader): every table in the schema, including ones created later.
-- To use it, delete the Option A line above and remove the leading "-- " below.
-- GRANT SELECT ON ALL    TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON FUTURE TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 7: Check the result
DESC USER LIFESIGHT;
SHOW GRANTS TO ROLE LIFESIGHT_READER;
```

6. Check the output of the last two lines:
   * `DESC USER LIFESIGHT` shows `TYPE` as `SERVICE`, a value in `RSA_PUBLIC_KEY_FP`, a default warehouse and role, and `HAS_PASSWORD` as `false`.
   * `SHOW GRANTS TO ROLE LIFESIGHT_READER` lists `USAGE` on the warehouse, database and schema, and `SELECT` on each table you granted. Nothing else.

The role can only read what you granted. It cannot write, create, change or delete anything.

To add a database, schema or table later, add the matching lines and run the script again.

#### Step 3: Copy the private key and keep it safe

1. Copy everything in `rsa_key.p8`, including the `BEGIN` and `END` lines:
   * **Mac:** run `pbcopy < rsa_key.p8` in Terminal. The key is now on your clipboard.
   * **Any computer:** open the file in a plain text editor such as TextEdit or Notepad, select all and copy.
2. Save it in your company password manager, such as 1Password or Bitwarden. Lifesight never shows the key again, so keep your own copy.
3. Delete the file from your computer.

Treat the private key like a password:

* Do not send it by email or chat. Share it through the password manager.
* If it is lost or shared by mistake, create a new key pair, put the new public key on the Snowflake user, and give Lifesight the new private key.

You should now have:

* the private key
* your account identifier
* the warehouse name
* the user (`LIFESIGHT`) and role (`LIFESIGHT_READER`)
* the databases and schemas you granted

> 📘 Does your Snowflake account restrict sign-in by IP?
>
> If your account uses a network policy, allow Lifesight's IP address `34.46.164.161`, or the connection test will fail.
>
> ```sql
> CREATE NETWORK POLICY LIFESIGHT_NETWORK_POLICY
>   ALLOWED_IP_LIST = ('34.46.164.161');
>
> ALTER USER LIFESIGHT SET NETWORK_POLICY = 'LIFESIGHT_NETWORK_POLICY';
> ```

***

## Connecting Snowflake

The setup has four steps.

### 1. Name and connect

1. Go to **Data > Integrations** and click **Add Integration**.
2. Open the **Data Warehouses** tab and click **Connect** on the Snowflake tile.

![The Data Warehouses tab with the Snowflake tile](https://files.readme.io/92c4a9953852d347d4ad0c052e6d1f09fbe2e3828f6a63360c1f974cdba78273-snowflake-data-warehouses.png)

3. Enter an **Integration Name**, for example `Paid media daily`. It is shown on your integrations list.

![The Name & Connect step of the Snowflake setup](https://files.readme.io/f63624857f5c7623cdd9864a72661d4b63f33e85074e2655428880ba4b2dda12-snowflake-name-and-connect.png)

4. Click **Add credential** and fill in the form:

| Field | What to enter |
| :-- | :-- |
| Credential name | Any name that helps you recognise this sign-in, for example `Acme analytics`. |
| Account identifier | Your account identifier, for example `acme-xy12345`. Not the full URL. |
| Warehouse | The warehouse name only, for example `LIFESIGHT_WH`. |
| Role (optional) | `LIFESIGHT_READER`. Leave empty to use the user's default role. |
| Username | `LIFESIGHT` |
| Passphrase (optional) | Leave empty, unless your private key is encrypted. |
| Private key | The private key you copied. |
| Databases and schemas | Every database and schema you granted. Click **Add database** for more. |

![The Add Snowflake credential dialog](https://files.readme.io/1354f72506e225a23919f5df430fe1aa0e2ffdbd2489d07092edcc490cb17aa2-snowflake-credential-form.png)

5. Click **Test and save**. Lifesight signs in and checks it can read each schema. The credential is saved only if the test passes.
6. Choose the **Database** and **Schema** for this integration.
7. Click **Verify and continue**.

### 2. Select a table

1. Find the table you want to bring in. Use the search box in a large schema.
2. Select it. Its columns and their types show on the right.
3. Click **Continue**.

![The Select a table step, with a table chosen and its columns listed on the right](https://files.readme.io/235d1fff60bfd448bef5bb33fdb061ba860c84fe150d24c3f2d3e14578fa86c4-snowflake-select-table.png)

Good to know:

* Each row shows the table's rows, columns, size and when it was last updated.
* A table that is already connected cannot be picked again, so the same data is never counted twice.
* If your table is missing, see [Troubleshooting](#databases-schemas-and-tables).

### 3. Data setup

1. Tell Lifesight how to read the table:

| What you confirm | What it means |
| :-- | :-- |
| Which column has the date? | The column Lifesight uses to read your data over time. It warns you if dates are inconsistent or missing. |
| Granularity | Whether each row is a day, a week or a month. |
| How is your data laid out? | **Stacked rows:** every row is one record, and channels are values in a column. **Pivoted columns:** every row is one date, and each channel has its own column. |
| What kind of data is this? | **Paid Marketing**, **KPI**, **Contextual**, **Organic** or **Other**. Other keeps the table for reference only. |
| Columns to import (optional) | All columns by default. Choose specific ones if you only need some. |

![The Data setup step, with the date column, granularity and layout choices](https://files.readme.io/bb982678c1a1aab40c282328f6b16826d98f53b6a47d0e137caab30587c3f433-snowflake-data-setup.png)

2. Check the **Preview** of the first rows to make sure it is the right table.

![The preview of the first rows of the table on the Data setup step](https://files.readme.io/b1e65f3d803911a2e6c43f4a6570176d48d4317d2b8275ab6913df19c3b16bea-snowflake-preview.png)

3. Click **Continue**.

### 4. Schedule and sync

1. Choose how often Lifesight refreshes the data:
   * **Daily:** set the time of day.
   * **Weekly:** set the day of the week and the time.
   * **Monthly:** set the day of the month and the time.

   Syncs are scheduled in UTC. The page also shows the time in your own time zone.
2. Choose how much to read each time:
   * **Full reload (recommended):** reads the whole table and replaces what was loaded before. Right for most tables.
   * **Incremental by date column:** reads only new rows, plus a few days back to pick up late changes. Use it for very large tables that have a date or timestamp column.
3. Click **Connect**.

The first sync starts straight away, then repeats on your schedule.

***

## After connecting

1. **Map the fields.** Open **Data > [Data Transformation](https://docs.lifesight.io/docs/4-data-transformation)**, find your Snowflake source and match its columns to Lifesight fields. Nothing is mapped until you do this. See [Map a field from a source](https://docs.lifesight.io/docs/map-field-from-source).
2. **Fill in what the table does not say.** If the whole table belongs to one channel or one country, set that once:
   * [Set a fixed value for a source](https://docs.lifesight.io/docs/fixed-value-source)
   * [Map a source to a channel](https://docs.lifesight.io/docs/map-source-channel)

> 👍 Bringing in more tables
>
> Click **Add Integration**, choose Snowflake and pick the same credential. You do not need another Snowflake user.

***

## Troubleshooting

### Signing in

| What you see | What to do |
| :-- | :-- |
| Snowflake rejected the sign-in | Check the username, and that the private key belongs to the public key set on that user. |
| Snowflake has no account with that name | Enter only the account identifier, not the full URL. |
| "JWT token is invalid" | The public key on the Snowflake user is missing or has line breaks. Run step 2 of the script again with the key as one line. |
| The private key is not accepted | The key must start with `-----BEGIN PRIVATE KEY-----`. If it starts with `-----BEGIN RSA PRIVATE KEY-----`, create it again with [Step 1](#step-1-create-the-two-key-files). |
| The test fails only from Lifesight | Your account probably has a network policy. Allow Lifesight's IP address `34.46.164.161`. |

### Role and warehouse

| What you see | What to do |
| :-- | :-- |
| The user cannot use the role | Grant the role to the user, or leave **Role** empty to use the user's default role. |
| The warehouse cannot be used | Check the warehouse name, and that the role has `USAGE` on it. |
| "No active warehouse" | Use the same warehouse name in the script and in Lifesight. |

### Databases, schemas and tables

| What you see | What to do |
| :-- | :-- |
| Lifesight cannot read a database or schema | Check the spelling, and that the role has `USAGE` on both the database and the schema. |
| My table is not listed | Check that the role has `SELECT` on it, that it is a table or materialized view, and that it is not already connected. |
| A table I added later does not appear | Add a `GRANT SELECT` line for it and run the script again, or use Option B. |

Still stuck? Contact Lifesight support and include the message you see.

***

## Next up

Connect your:

* Google Sheets
* CSV Import
* Google Ads