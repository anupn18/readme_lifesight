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

Lifesight signs in to Snowflake as a service user with a key pair, not a password. You create the user once.

1. Generate a key pair on your computer. This creates a private key (`rsa_key.p8`) and a public key (`rsa_key.pub`).

```bash
openssl genrsa 2048 | openssl pkcs8 -topk8 -inform PEM -out rsa_key.p8 -nocrypt
openssl rsa -in rsa_key.p8 -pubout -out rsa_key.pub
```

2. In Snowflake, open a new SQL worksheet and run the script below. Replace the values in angle brackets. For the public key, paste the contents of `rsa_key.pub` without the `BEGIN` and `END` lines and without line breaks.

```sql
USE ROLE ACCOUNTADMIN;

-- A read-only role for Lifesight
CREATE ROLE IF NOT EXISTS LIFESIGHT_READER;

-- A service user that signs in with the key pair
CREATE USER IF NOT EXISTS SVC_LIFESIGHT
  TYPE = SERVICE
  DEFAULT_ROLE = LIFESIGHT_READER
  DEFAULT_WAREHOUSE = <WAREHOUSE_NAME>
  RSA_PUBLIC_KEY = '<PUBLIC_KEY>';

GRANT ROLE LIFESIGHT_READER TO USER SVC_LIFESIGHT;

-- What Lifesight is allowed to read
GRANT USAGE ON WAREHOUSE <WAREHOUSE_NAME> TO ROLE LIFESIGHT_READER;
GRANT USAGE ON DATABASE <DATABASE_NAME> TO ROLE LIFESIGHT_READER;
GRANT USAGE ON SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;
GRANT SELECT ON ALL TABLES IN SCHEMA <DATABASE_NAME>.<SCHEMA_NAME> TO ROLE LIFESIGHT_READER;

-- To share one table only, use this line instead of the one above:
-- GRANT SELECT ON TABLE <DATABASE_NAME>.<SCHEMA_NAME>.<TABLE_NAME> TO ROLE LIFESIGHT_READER;
```

3. Keep the private key file (`rsa_key.p8`) to hand. You paste it into Lifesight in the next section.

Repeat the three `GRANT` lines for each extra database or schema you want Lifesight to read.

> 📘 Does your Snowflake account restrict sign-in by IP?
>
> If your account uses a network policy, allow Lifesight's IP address `34.46.164.161` for this user, or the connection test will fail.
>
> ```sql
> CREATE NETWORK POLICY LIFESIGHT_NETWORK_POLICY
>   ALLOWED_IP_LIST = ('34.46.164.161');
>
> ALTER USER SVC_LIFESIGHT SET NETWORK_POLICY = 'LIFESIGHT_NETWORK_POLICY';
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
| Username | The service user, for example `SVC_LIFESIGHT`. |
| Passphrase (optional) | Only if your private key is encrypted. |
| Private key | The full contents of `rsa_key.p8`, starting with `-----BEGIN PRIVATE KEY-----`. |
| Databases and schemas | Every database and schema you want to read. Click **Add database** for more. |

![The Add Snowflake credential dialog](https://files.readme.io/873ef6f3e89c79e112178eaa6523549186a5ce61c9a64af8ec36fe9024f5fe44-snowflake-add-credential.png)

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