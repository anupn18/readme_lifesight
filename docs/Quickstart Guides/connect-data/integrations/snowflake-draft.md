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
Snowflake is the cloud data warehouse where many teams keep the data that does not live in an ad platform: orders and revenue, organic and CRM activity, pricing, promotions, and spend from channels with no connector of their own.

Connecting Snowflake lets Lifesight read those tables directly on a schedule, so nobody has to export and upload files, and warehouse data sits alongside every other source in your measurement.

## What Lifesight brings in

Lifesight reads the tables you choose, and nothing else:

* **Tables and materialized views** in the databases and schemas you give access to.
* **One table per integration.** To bring in several tables, add an integration for each and reuse the same credential.
* **Read only.** Lifesight never writes to, changes or deletes anything in Snowflake.

Any kind of data can come through Snowflake. You tell Lifesight which kind each table holds when you connect it:

| Kind of data | Examples |
| :-- | :-- |
| Paid Marketing | Spend, impressions and clicks from channels without a native connector |
| KPI | Revenue, orders, leads, sign-ups |
| Organic | Email sends, organic social, search visibility |
| Contextual | Pricing, promotions, seasonality, stock levels |

## Before you start

You need three things.

* **Someone with admin rights in Snowflake**, to create a user for Lifesight. Running the script below as `ACCOUNTADMIN` is the simplest way.
* **Your account identifier.** This is the part of your Snowflake URL before `.snowflakecomputing.com`. In `acme-xy12345.snowflakecomputing.com`, it is `acme-xy12345`.
* **The names of the warehouse, databases, schemas and tables** you want Lifesight to read. An X-Small warehouse is enough.

### Creating a Snowflake user for Lifesight

Lifesight signs in to Snowflake as its own user, with a key pair instead of a password. You set this up once.

> 👍 You do not have to do this yourself
>
> This part is usually done by whoever looks after Snowflake at your company, such as your data or IT team. Send them a link to this section. It takes about ten minutes, and they send you back one file (the private key) plus the names you need for the form.

**What is a key pair?** Two small text files that belong together. The **public key** goes on the Snowflake user, like a lock. The **private key** goes into Lifesight, like the key that opens it. Only the private key is secret.

#### Step 1: Create the two key files

1. Open the **Terminal** app. On a Mac, press `Cmd + Space`, type `Terminal` and press Enter. On Windows, use **Git Bash**, or ask your IT team to run this step.
2. Copy the two lines below, paste them into Terminal and press Enter.

```bash
openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

Two new files now sit in your home folder:

| File | What it is | Where it goes |
| :-- | :-- | :-- |
| `rsa_key.pub` | The public key. Not secret. | Into the Snowflake script in step 2. |
| `rsa_key.p8` | The private key. Keep it secret. | Into Lifesight, when you add the credential. |

Both are plain text. Opened in a text editor, the public key looks like this. The private key looks the same, but is longer and says `PRIVATE KEY`.

```text
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAu7Tq9xw2LkP4vGm1Zc8H
Rn3JfQyE6bWdS0aKtNvXo5Ll2pMhCzYs9gUeI1AjB7rFxD4kVtq8ZnWmPc3oRbLy
... a few more lines like these ...
8QIDAQAB
-----END PUBLIC KEY-----
```

#### Step 2: Create the user in Snowflake

1. Get the public key ready to paste. Snowflake wants it as one line, without the `BEGIN` and `END` lines. This command prints it in exactly that form. Select the output and copy it.

```bash
grep -v "PUBLIC KEY" rsa_key.pub | tr -d '\n'
```

2. In Snowflake, click **+** and open a new **SQL Worksheet**.
3. Paste the script below. Replace each value in angle brackets with your own, and paste the public key in place of `<PUBLIC_KEY>`, keeping the quotes around it.
4. Run the whole script.

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
GRANT ROLE LIFESIGHT_READER TO ROLE SYSADMIN;   -- lets your own admins manage it later
ALTER USER LIFESIGHT SET DEFAULT_ROLE = LIFESIGHT_READER;

-- STEP 4: Let the role use the warehouse
GRANT USAGE ON WAREHOUSE <WAREHOUSE_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 5: Let the role see the database and schema (this gives no data access)
-- Repeat the SCHEMA line for each extra schema.
GRANT USAGE ON DATABASE <DATABASE_NAME>               TO ROLE LIFESIGHT_READER;
GRANT USAGE ON SCHEMA   <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 6: Give read access to your data. Choose ONE option.

-- OPTION A: only the tables you list. One line per table or view.
GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME_2> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON VIEW  <DATABASE_NAME>.<SCHEMA_NAME>.<VIEW_NAME>    TO ROLE LIFESIGHT_READER;

-- OPTION B: every table and view in the schema, including ones created later.
-- To use it, delete the Option A line above and remove the leading "-- " below.
-- GRANT SELECT ON ALL    TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON FUTURE TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON ALL    VIEWS  IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
-- GRANT SELECT ON FUTURE VIEWS  IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- STEP 7: Check the result
DESC USER LIFESIGHT;
SHOW GRANTS TO ROLE LIFESIGHT_READER;
```

**Which read access should I choose?**

| Option | What Lifesight can read | Choose it when |
| :-- | :-- | :-- |
| A: listed tables | Only the tables and views you name, one line each. | You want to share as little as possible. |
| B: the whole schema | Every table and view in the schema, including any created in future. | New tables appear regularly and you do not want to come back to this script. |

**Check it worked.** The last two lines of the script print what was set up:

* `DESC USER LIFESIGHT` should show `TYPE` as `SERVICE`, a value in `RSA_PUBLIC_KEY_FP`, a default warehouse and role, and `HAS_PASSWORD` as `false`.
* `SHOW GRANTS TO ROLE LIFESIGHT_READER` should list `USAGE` on the warehouse, database and schema, and `SELECT` on each table or view you granted.

To add another database, schema or table later, add the matching lines and run the script again.

#### Step 3: Copy the private key and keep it safe

The private key is what you paste into Lifesight. Copy all of it, including the `-----BEGIN PRIVATE KEY-----` and `-----END PRIVATE KEY-----` lines.

* **On a Mac,** this command copies the whole file to your clipboard, ready to paste:

```bash
pbcopy < rsa_key.p8
```

* **On any computer,** open `rsa_key.p8` in a plain text editor such as TextEdit or Notepad, select everything and copy it.

Treat the private key like a password:

* **Save it in your company password manager**, such as 1Password or Bitwarden. Lifesight stores it encrypted and never shows it again, so keep your own copy.
* **Do not send it by email or chat.** If a teammate created it for you, ask them to share it through the password manager.
* **Delete the file from your computer** once it is saved in the password manager.
* **If it is ever lost or shared by mistake,** create a new key pair, put the new public key on the Snowflake user, and give Lifesight the new private key.

When this is done, you should have these to hand for the next section: the private key, your account identifier, the warehouse name, the user name (`LIFESIGHT`), the role (`LIFESIGHT_READER`), and the databases and schemas you granted.

> 📘 Does your Snowflake account restrict sign-in by IP?
>
> If your account uses a network policy, allow Lifesight's IP address `34.46.164.161` for this user, or the connection test will fail.
>
> ```sql
> CREATE NETWORK POLICY LIFESIGHT_NETWORK_POLICY
>   ALLOWED_IP_LIST = ('34.46.164.161');
>
> ALTER USER LIFESIGHT SET NETWORK_POLICY = 'LIFESIGHT_NETWORK_POLICY';
> ```

## Connecting Snowflake

1. Go to **Data > Integrations** and click **Add Integration**.
2. Open the **Data Warehouses** tab and click **Connect** on the Snowflake tile.

![The Data Warehouses tab with the Snowflake tile](https://files.readme.io/92c4a9953852d347d4ad0c052e6d1f09fbe2e3828f6a63360c1f974cdba78273-snowflake-data-warehouses.png)

3. On the **Name & Connect** step, enter an **Integration Name**. This is the name shown on your integrations list, so name it after the data, for example `Paid media daily`.

![The Name & Connect step of the Snowflake setup](https://files.readme.io/f63624857f5c7623cdd9864a72661d4b63f33e85074e2655428880ba4b2dda12-snowflake-name-and-connect.png)

4. Click **Add credential** and fill in the details of the user you created.

| Field | What to enter |
| :-- | :-- |
| Credential name | Any name that helps you recognise this sign-in, for example `Acme analytics`. |
| Account identifier | The part of your Snowflake URL before `.snowflakecomputing.com`. |
| Warehouse | The warehouse name only, for example `LIFESIGHT_WH`. |
| Role (optional) | The role to use, for example `LIFESIGHT_READER`. Leave empty to use the user's default role. |
| Username | The service user, for example `LIFESIGHT`. |
| Passphrase (optional) | Only if your private key is encrypted. |
| Private key | Everything in `rsa_key.p8`, from `-----BEGIN PRIVATE KEY-----` to `-----END PRIVATE KEY-----`. |
| Databases and schemas | Every database and schema you want to read. Click **Add database** for more. |

![The Add Snowflake credential dialog](https://files.readme.io/1354f72506e225a23919f5df430fe1aa0e2ffdbd2489d07092edcc490cb17aa2-snowflake-credential-form.png)

5. Click **Test and save**. Lifesight signs in to Snowflake and checks that it can read each schema you listed. The credential is saved only when the test passes. Your private key is stored encrypted and is never shown again.
6. Choose the **Database** and **Schema** for this integration, then click **Verify and continue**.
7. On **Select tables**, pick the table you want to bring in. Its columns show on the right.
8. On **Data setup**, check the sample rows, choose the column that holds the date, and pick what kind of data this is.
9. On **Schedule & sync**, choose how often Lifesight should refresh the data: **Daily**, **Weekly**, **Monthly** or **Manual**.
10. Click **Connect**.

The first sync starts as soon as you connect, then repeats on your schedule.

## After connecting

**Map the fields -** Open **Data > Data Transformation**, find your Snowflake source, and map its columns to Lifesight fields. Warehouse tables use your own column names, so nothing is mapped until you do this.

**Add more tables -** Each integration reads one table. To bring in another, add a new Snowflake integration and pick the same credential. You do not need to create another user.

***

## Troubleshooting

**Snowflake rejected the sign-in**<br />Check the username, and that the private key you pasted belongs to the public key set on that user. If you regenerated the key pair, update the user in Snowflake with the new public key.

**Snowflake has no account with that name**<br />Enter only the account identifier, the part before `.snowflakecomputing.com`, not the full URL.

**The user cannot use the role**<br />Make sure the role was granted to the user, or leave **Role** empty to use the user's default role.

**"JWT token is invalid"**<br />The public key on the Snowflake user is missing or was pasted with the `BEGIN` and `END` lines or with line breaks. Run step 2 of the script again with the key as a single line, and check that `RSA_PUBLIC_KEY_FP` has a value in `DESC USER`.

**"No active warehouse"**<br />The warehouse in the script is not the one you entered in Lifesight. Use the same name in both.

**The warehouse cannot be used**<br />Check the warehouse name and that the role has `USAGE` on it.

**Lifesight cannot read a database or schema**<br />Check the spelling against Snowflake, and that the role has `USAGE` on both the database and the schema.

**My table is not listed**<br />Only tables and materialized views are shown. Check that the role has `SELECT` on the table, and that the table is not already connected through another integration.

**The private key is not accepted**<br />Lifesight needs the key in PKCS#8 format, which starts with `-----BEGIN PRIVATE KEY-----`. A key that starts with `-----BEGIN RSA PRIVATE KEY-----` is in an older format. Generate it again with the commands above.

**The test fails only from Lifesight**<br />Your account probably has a network policy. Allow Lifesight's IP address as described in Before you start.

***

## Next up

Connect your:

* Google Sheets
* CSV Import
* Google Ads