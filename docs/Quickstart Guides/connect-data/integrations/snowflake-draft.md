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

## The steps at a glance

There are seven steps, in two parts.

**Part 1: Set up the Snowflake credential.** Done once. It needs someone who manages Snowflake, so most marketers hand this part to their IT or data team.

| Step | What happens | Who does it |
| :-- | :-- | :-- |
| [Step 1: Create the two key files](#step-1-create-the-two-key-files) | Two key files are created. Lifesight uses them to sign in instead of a password. | Your IT or data team, or you |
| [Step 2: Create the user in Snowflake](#step-2-create-the-user-in-snowflake) | A script creates a read-only Snowflake user for Lifesight. | Your IT or data team, or you |
| [Step 3: Save the private key](#step-3-save-the-private-key) | The private key is stored safely and passed to whoever does Part 2. | Your IT or data team, or you |

**Part 2: Connect Snowflake in Lifesight.** Done for each table. No Snowflake knowledge needed.

| Step | What happens | Who does it |
| :-- | :-- | :-- |
| [Step 4: Name and connect](#step-4-name-and-connect) | You name the integration and add the credential from Part 1. | You |
| [Step 5: Select a table](#step-5-select-a-table) | You pick the table to bring in. | You |
| [Step 6: Set up the data](#step-6-set-up-the-data) | You tell Lifesight how to read the table. | You |
| [Step 7: Schedule and sync](#step-7-schedule-and-sync) | You choose how often the data refreshes. | You |

Also on this page: [What Lifesight brings in](#what-lifesight-brings-in), [After connecting](#after-connecting) and [Troubleshooting](#troubleshooting).

***

## What Lifesight brings in

| | |
| :-- | :-- |
| **What it reads** | Only the tables and materialized views you choose. |
| **How many** | One table per integration. Add an integration for each table and reuse the same credential. |
| **What it can do** | Read only. Lifesight never writes to, changes or deletes anything in Snowflake. |
| **Kinds of data** | Paid Marketing, KPI, Organic or Contextual. You choose the kind for each table in step 6. |

***

## Before you start

| You need | Details |
| :-- | :-- |
| A Snowflake admin | Someone who can run a script as `ACCOUNTADMIN`. This can be you or your data or IT team. |
| Your account identifier | The part of your Snowflake URL before `.snowflakecomputing.com`. In `acme-xy12345.snowflakecomputing.com`, it is `acme-xy12345`. |
| A warehouse name | An X-Small warehouse is enough. |
| The database, schema and table names | What you want Lifesight to read. |

***

## Part 1: Set up the Snowflake credential

Lifesight signs in to Snowflake as its own read-only user, with a key pair instead of a password. You do this part once.

> 👍 You do not have to do this yourself
>
> Send this part to whoever looks after Snowflake at your company. It takes about ten minutes. They send you back the private key and the names you need in step 4.

### Step 1: Create the two key files

1. Open a terminal:
   * **Mac:** press `Cmd + Space`, type `Terminal` and press Enter.
   * **Windows:** open **Git Bash**, or ask your IT team to run this step.
2. Paste these two lines and press Enter:

```bash
openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

**Result:** two new files in your home folder.

| File | What it is | Used in |
| :-- | :-- | :-- |
| `rsa_key.pub` | The public key. Not secret. | Step 2 |
| `rsa_key.p8` | The private key. Keep it secret. | Steps 3 and 4 |

> 📘 What a key file looks like
>
> Both are plain text. The private key looks the same as this one, but is longer and says `PRIVATE KEY`.
>
> ```text
> -----BEGIN PUBLIC KEY-----
> MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAu7Tq9xw2LkP4vGm1Zc8H
> ... a few more lines like this ...
> 8QIDAQAB
> -----END PUBLIC KEY-----
> ```

### Step 2: Create the user in Snowflake

1. Print the public key as one line, the form Snowflake needs. Run this in the terminal, then copy the output:

```bash
grep -v "PUBLIC KEY" rsa_key.pub | tr -d '\n'
```

2. In Snowflake, click **+** and open a new **SQL Worksheet**.
3. Paste the script below into the worksheet.
4. Replace each placeholder:

| Placeholder | Replace with |
| :-- | :-- |
| `<WAREHOUSE_NAME>` | Your warehouse |
| `<DATABASE_NAME>` and `<SCHEMA_NAME>` | Where your data is |
| `<TABLE_NAME>` | The table to share |
| `<PUBLIC_KEY>` | The line you copied in action 1, inside the quotes |

5. Choose the read access in section 6 of the script:

| Option | What Lifesight can read | Choose it when |
| :-- | :-- | :-- |
| A (recommended) | Only the tables you name, one line each | You want to share as little as possible. This is all Lifesight needs. |
| B | Every table in the schema, including ones created later | New tables appear regularly |

6. Run the whole script as `ACCOUNTADMIN`.

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

-- SECTION 1: Create the service user
USE ROLE USERADMIN;

CREATE USER IF NOT EXISTS LIFESIGHT
  LOGIN_NAME   = 'LIFESIGHT'
  DISPLAY_NAME = 'Lifesight Integration'
  COMMENT      = 'Read-only service user for the Lifesight integration';

-- SECTION 2: Key-pair sign-in, user type and default warehouse
-- These run every time, so they also apply if the user already existed.
ALTER USER LIFESIGHT UNSET PASSWORD;
ALTER USER LIFESIGHT SET TYPE = SERVICE;
ALTER USER LIFESIGHT SET
  DEFAULT_WAREHOUSE = <WAREHOUSE_NAME>
  RSA_PUBLIC_KEY    = '<PUBLIC_KEY>';
-- ^ The public key as one line, without the BEGIN/END lines or line breaks.

-- SECTION 3: Create the read-only role and give it to the user
USE ROLE SECURITYADMIN;

CREATE ROLE IF NOT EXISTS LIFESIGHT_READER;
GRANT ROLE LIFESIGHT_READER TO USER LIFESIGHT;
ALTER USER LIFESIGHT SET DEFAULT_ROLE = LIFESIGHT_READER;

-- SECTION 4: Let the role use the warehouse
GRANT USAGE ON WAREHOUSE <WAREHOUSE_NAME> TO ROLE LIFESIGHT_READER;

-- SECTION 5: Let the role see the database and schema (this gives no data access)
-- Repeat the SCHEMA line for each extra schema.
GRANT USAGE ON DATABASE <DATABASE_NAME>               TO ROLE LIFESIGHT_READER;
GRANT USAGE ON SCHEMA   <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- SECTION 6: Give read access to your data. Choose ONE option.
-- Lifesight only needs SELECT on the tables you want to sync.

-- OPTION A (recommended): only the tables you list. One line per table.
GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME_2> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON MATERIALIZED VIEW <DATABASE_NAME>.<SCHEMA_NAME>.<VIEW_NAME> TO ROLE LIFESIGHT_READER;

-- OPTION B (broader): every table in the schema, including ones created later.
-- To use it, delete the Option A line above and remove the leading "-- " below.
-- GRANT SELECT ON ALL    TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON FUTURE TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- SECTION 7: Check the result
DESC USER LIFESIGHT;
SHOW GRANTS TO ROLE LIFESIGHT_READER;
```

7. Check the output of the last two lines:

| Line | It should show |
| :-- | :-- |
| `DESC USER LIFESIGHT` | `TYPE` is `SERVICE`, `RSA_PUBLIC_KEY_FP` has a value, `HAS_PASSWORD` is `false` |
| `SHOW GRANTS TO ROLE LIFESIGHT_READER` | `USAGE` on the warehouse, database and schema, and `SELECT` on each table you granted. Nothing else. |

**Result:** the user `LIFESIGHT` exists with the role `LIFESIGHT_READER`, and can only read what you granted.

> 📘 Adding more later
>
> To add a database, schema or table, add the matching lines and run the script again. It is safe to run more than once.

> 🚧 Does your Snowflake account restrict sign-in by IP?
>
> If your account uses a network policy, also run this, or the connection test in step 4 will fail. Lifesight's IP address is `34.46.164.161`.
>
> ```sql
> CREATE NETWORK POLICY LIFESIGHT_NETWORK_POLICY
>   ALLOWED_IP_LIST = ('34.46.164.161');
>
> ALTER USER LIFESIGHT SET NETWORK_POLICY = 'LIFESIGHT_NETWORK_POLICY';
> ```

### Step 3: Save the private key

1. Copy everything in `rsa_key.p8`, including the `BEGIN` and `END` lines:
   * **Mac:** run `pbcopy < rsa_key.p8` in the terminal. The key is now on your clipboard.
   * **Windows:** open the file in Notepad, select all and copy.
2. Save it in your company password manager, such as 1Password or Bitwarden.
3. Delete `rsa_key.p8` from your computer.

**Result:** the private key is stored safely and ready to paste in step 4.

> 🚧 Treat the private key like a password
>
> Do not send it by email or chat. Share it through the password manager. Lifesight never shows the key again, so keep your copy. If it is lost or shared by mistake, repeat steps 1 to 3 to create a new one.

**Before you go on to Part 2, check you have:**

| What | Example |
| :-- | :-- |
| Private key | Saved in your password manager |
| Account identifier | `acme-xy12345` |
| Warehouse | `LIFESIGHT_WH` |
| User | `LIFESIGHT` |
| Role | `LIFESIGHT_READER` |
| Databases and schemas | `ANALYTICS` with `MARKETING` |

***

## Part 2: Connect Snowflake in Lifesight

You do this part for each table you want to bring in. The credential from Part 1 is reused every time.

### Step 4: Name and connect

1. Go to **Data > Integrations** and click **Add Integration**.
2. Open the **Data Warehouses** tab and click **Connect** on the Snowflake tile.

![The Data Warehouses tab with the Snowflake tile](https://files.readme.io/92c4a9953852d347d4ad0c052e6d1f09fbe2e3828f6a63360c1f974cdba78273-snowflake-data-warehouses.png)

3. Enter an **Integration Name**, for example `Paid media daily`.

![The Name & Connect step of the Snowflake setup](https://files.readme.io/f63624857f5c7623cdd9864a72661d4b63f33e85074e2655428880ba4b2dda12-snowflake-name-and-connect.png)

4. Click **Add credential** and fill in the form:

| Field | What to enter |
| :-- | :-- |
| Credential name | Any name that helps you recognise this sign-in, for example `Acme analytics` |
| Account identifier | Your account identifier. Not the full URL. |
| Warehouse | Your warehouse name |
| Role (optional) | `LIFESIGHT_READER` |
| Username | `LIFESIGHT` |
| Passphrase (optional) | Leave empty |
| Private key | Paste the private key from your password manager |
| Databases and schemas | Every database and schema you granted. Click **Add database** for more. |

![The Add Snowflake credential dialog](https://files.readme.io/1354f72506e225a23919f5df430fe1aa0e2ffdbd2489d07092edcc490cb17aa2-snowflake-credential-form.png)

5. Click **Test and save**.
6. Choose the **Database** and **Schema** for this integration.
7. Click **Verify and continue**.

**Result:** the credential is saved and you move to the table list. If the test fails, see [Troubleshooting](#troubleshooting).

> 📘 Next time, skip the form
>
> The credential is saved. For your next table, pick it from the list in action 4.

### Step 5: Select a table

1. Find the table you want. Use the search box in a large schema.
2. Select it. Its columns and their types show on the right.
3. Click **Continue**.

![The Select a table step, with a table chosen and its columns listed on the right](https://files.readme.io/235d1fff60bfd448bef5bb33fdb061ba860c84fe150d24c3f2d3e14578fa86c4-snowflake-select-table.png)

> 📘 Cannot pick a table?
>
> A table that is already connected cannot be picked again, so the same data is never counted twice. If your table is not in the list, see [Troubleshooting](#databases-schemas-and-tables).

### Step 6: Set up the data

1. Answer the questions about your table:

| Question | What to choose |
| :-- | :-- |
| Which column has the date? | The column that says which day, week or month each row belongs to |
| Granularity | Daily, Weekly or Monthly |
| How is your data laid out? | **Stacked rows**: every row is one record, and channels appear as values in a column |
| What kind of data is this? | Paid Marketing, KPI, Contextual, Organic or Other. Other keeps the table for reference only. |
| Columns to import (optional) | All columns, or only the ones you need |

![The Data setup step, with the date column, granularity and layout choices](https://files.readme.io/9abe23b1e9ff5ddfb54f1c20280af7b224d647da43f8c8849b7f07058a4eba96-snowflake-data-setup-stacked.png)

2. Check the **Preview** to make sure it is the right table.

![The preview of the first rows of the table on the Data setup step](https://files.readme.io/b1e65f3d803911a2e6c43f4a6570176d48d4317d2b8275ab6913df19c3b16bea-snowflake-preview.png)

3. Click **Continue**.

### Step 7: Schedule and sync

1. Choose how often Lifesight refreshes the data:

| Frequency | What you set |
| :-- | :-- |
| Daily | The time of day |
| Weekly | The day of the week and the time |
| Monthly | The day of the month and the time |

2. Choose how much to read each time:

| Option | What it does | Use it for |
| :-- | :-- | :-- |
| Full reload (recommended) | Reads the whole table and replaces what was loaded before | Most tables |
| Incremental by date column | Reads only new rows, plus a few days back for late changes | Very large tables with a date or timestamp column |

3. Click **Connect**.

**Result:** the integration is connected. The first sync starts straight away, then repeats on your schedule.

***

## After connecting

| Next | What to do | Guide |
| :-- | :-- | :-- |
| Map the fields | Open **Data > Data Transformation**, find your Snowflake source and match its columns to Lifesight fields. Nothing is mapped until you do this. | [Data Transformation](https://docs.lifesight.io/docs/4-data-transformation), [Map a field from a source](https://docs.lifesight.io/docs/map-field-from-source) |
| Fill in what the table does not say | If the whole table belongs to one channel or one country, set that once. | [Set a fixed value for a source](https://docs.lifesight.io/docs/fixed-value-source), [Map a source to a channel](https://docs.lifesight.io/docs/map-source-channel) |
| Bring in another table | Repeat steps 4 to 7 and pick the same credential. You do not need another Snowflake user. | [Part 2](#part-2-connect-snowflake-in-lifesight) |

***

## Troubleshooting

### Signing in

| What you see | What to do |
| :-- | :-- |
| Snowflake rejected the sign-in | Check the username, and that the private key belongs to the public key set on that user. |
| Snowflake has no account with that name | Enter only the account identifier, not the full URL. |
| "JWT token is invalid" | The public key on the Snowflake user is missing or has line breaks. Run section 2 of the script again with the key as one line. |
| The private key is not accepted | The key must start with `-----BEGIN PRIVATE KEY-----`. If it starts with `-----BEGIN RSA PRIVATE KEY-----`, repeat [step 1](#step-1-create-the-two-key-files). |
| The test fails only from Lifesight | Your account probably has a network policy. Allow Lifesight's IP address `34.46.164.161`, as shown in [step 2](#step-2-create-the-user-in-snowflake). |

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