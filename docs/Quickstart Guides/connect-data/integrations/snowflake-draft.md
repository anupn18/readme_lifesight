---
title: Snowflake
excerpt: >-
  Connect Snowflake so the tables your data team already maintains refresh into
  Lifesight on a schedule.
deprecated: false
hidden: true
metadata:
  robots: index
---
If your spend, orders or offline sales are already modeled in Snowflake, there is no reason to export them. Lifesight reads the table directly, on the schedule you set, and only ever reads. It cannot write to, change or delete anything in your account.

Setting it up has two parts, and it helps to keep them apart:

**A credential** is the saved sign-in: your account, the warehouse, and the databases and schemas Lifesight may read. You set it up once.

**An integration** is one feed of data read through a credential. Each Snowflake integration syncs one table. To sync a second table, add another integration and pick the same credential again.

## Before you start

You will need:

* **Someone who can run a worksheet as `ACCOUNTADMIN`.** Creating the credential involves running one setup script in Snowflake. If that is not you, send the script to your Snowflake admin.
* **Your account identifier.** The part of your Snowflake URL before `.snowflakecomputing.com`, for example `acme-xy12345`.
* **A warehouse.** It runs Lifesight's read queries. An X-Small warehouse is enough.
* **The databases, schemas and tables you want to sync.** Names only, exactly as they were created.

You do not need to create a user, a password or a key pair. Lifesight signs in with key-pair authentication as a read-only service user that the setup script creates for you, and Lifesight holds the private key. Nothing secret is typed or pasted at any point.

> 📘 Why no password?
>
> Snowflake is blocking password sign-in for service users from 2026. Key-pair sign-in on a `SERVICE` user is exempt from the MFA requirement, so the connection keeps working.

## Adding a Snowflake credential

A credential is saved only once it passes a connection test, so the order is: fill in the form, run the setup script in Snowflake, then test.

1. Go to **Data > Integrations** and click **Add Integration**.
2. Find **Snowflake** under **Data Warehouses**, or search for it, and click **Connect**.
3. On the first step, **Name & Connect**, click **Add credential**.
4. Fill in the fields below.

![The Data Warehouses tab of Add Integration, showing Snowflake and BigQuery](https://files.readme.io/52c381587621b90956d4444442f1443b024ec634b574a3066e6c9fd6c00a2872-01-add-integration-data-warehouses.jpg)

![Step 1 of the Snowflake wizard, Name & Connect, with the Add credential button](https://files.readme.io/7c8551e6b88e6618255ecb3364e22cc049d9e1823a916f118839c51d9b81fd42-02-step1-name-and-connect.jpg)

![The Add Snowflake credential dialog with its fields filled in](https://files.readme.io/444a3b5f0737f5cdc4001d917b3de420e17138e7cb2785b1070e9eae1aea8ee9-03-add-credential.jpg)

| Field | What to enter | Example |
| :-- | :-- | :-- |
| Credential name | A name for this saved sign-in. It has to be unique in your workspace. | `Acme analytics` |
| Account identifier | The part of your Snowflake URL before `.snowflakecomputing.com`. Not the full URL. | `acme-xy12345` |
| Warehouse | The warehouse that runs Lifesight's queries. The name only, with no database in front. | `LIFESIGHT_WH` |
| Databases and schemas | Every database this credential should read, and the schemas in each. Click **Add database** to list more than one. | `ANALYTICS` with `MARKETING`, `FINANCE` |

List every database and schema you plan to read, not only the first one. The credential is shared, and each integration later picks one database and one schema from this list.

**Names follow Snowflake's rules.** They start with a letter or underscore and use letters, digits, `_` and `$`. Wrap any other name, such as one with spaces or lowercase letters, in double quotes exactly as it was created. Enter each name on its own: `ANALYTICS.MARKETING` is rejected, so enter `ANALYTICS` as the database and `MARKETING` as a schema.

If a value does not fit these rules, the field says what to fix before you can test.

![The credential dialog showing validation messages for a duplicate name, a pasted URL and qualified names](https://files.readme.io/96e85f0c29fec310bac3ad839f079dfc3b64ed790c0371e929e0fd279e2f9459-06-validation-errors.jpg)

The user and role are not fields. Lifesight always signs in as the user `LIFESIGHT` with the role `LS_ADMIN`, and the setup script creates both.

## Running the setup script

Below the fields, the **Setup script** section holds the SQL that gives Lifesight access. It is built from what you typed, so the warehouse, databases and schemas are already filled in.

![The Setup script section, with Grant read on set to One table and all placeholders filled](https://files.readme.io/ce85f4661b1fad2981b09f99fe89b4a2983eed9d6ec92da1197a604460441eb9-04-setup-script.jpg)

1. Under **Grant read on**, choose how much Lifesight may read:
   * **One table** grants `SELECT` on a single named table in each schema. Type the table name in the **Table** field. This is the narrowest access.
   * **All tables** grants `SELECT` on every current and future table and view in each schema you listed. Choose this if new tables appear regularly.
2. Check the **Still to fill** line. Any placeholder shown there, such as `<TABLE_NAME>`, is still empty in the script. When nothing is left, it reads **All placeholders are filled**.
3. Click **Copy**. Lifesight's public key is added to the script when you copy it. The script on screen keeps a placeholder for the key so it stays short.
4. Open a worksheet in Snowflake, paste the script, and run the whole thing as `ACCOUNTADMIN`.
5. Back in Lifesight, click **Test and save**.

When the test passes, the dialog closes and the credential is selected, marked **Access verified** with the number of databases and schemas it can read.

The script is safe to run again. It never removes grants that already exist, so you can re-run it after adding a database, schema or table.

### What the script does

| Step | What happens in Snowflake |
| :-- | :-- |
| 1 | Creates the user `LIFESIGHT`, if it does not already exist. |
| 2 | Removes any password, sets the user's type to `SERVICE`, and sets its default warehouse and Lifesight's RSA public key. |
| 3 | Creates the role `LS_ADMIN`, grants it to `LIFESIGHT` and to `SYSADMIN`, and makes it the user's default role. |
| 4 | Grants `USAGE` on the warehouse. |
| 5 | Grants `USAGE` on each database and schema. This makes them visible, and grants no access to data. |
| 6 | Grants `SELECT` on the tables and views you chose. |
| 7 | Runs `DESC USER LIFESIGHT` and `SHOW GRANTS TO ROLE LS_ADMIN` so you can check the result. |

### Checking it worked

The last two statements print what was set up. Before you return to Lifesight, confirm that:

* `DESC USER LIFESIGHT` shows `TYPE = SERVICE`, a value in `RSA_PUBLIC_KEY_FP`, a default warehouse and role, and `HAS_PASSWORD = false`.
* `SHOW GRANTS TO ROLE LS_ADMIN` shows `USAGE` on the warehouse, the database and each schema, and `SELECT` on each table or view you granted.

### If your account restricts sign-in by IP

If your Snowflake account uses a network policy, allow Lifesight's IP address `35.206.86.230`, or the user will not be able to sign in. The optional **Firewall** section of the credential dialog has the script ready to copy:

![The Firewall section of the credential dialog, with the network policy script](https://files.readme.io/80593f5b816e4b93496e8e334795841aa1afcb510f1f77160f02b87979b61352-05-firewall.jpg)

```sql
CREATE NETWORK POLICY LIFESIGHT_NETWORK_POLICY
  ALLOWED_IP_LIST = ('35.206.86.230')
  COMMENT = 'Restrict Lifesight to specific IP only';

ALTER USER LIFESIGHT SET NETWORK_POLICY = 'LIFESIGHT_NETWORK_POLICY';
```

***

## Connecting a table

With a credential in place, the wizard has four steps: **Name & Connect**, **Select tables**, **Data setup**, and **Schedule & sync**.

### 1. Name & Connect

1. Enter an **Integration Name**. This is what shows on your integrations list, so name it after the data, for example `Paid media daily`. The **Note** is optional and shows as a tooltip on the name.
2. Pick the **Credential**. Search by name or account, or click **Add credential** to create one. Credentials are grouped by state: **Access verified** ones can read everything they list, and **Partial access** ones still work but have lost access to some of what they list.
3. Choose the **Database** and **Schema** this integration reads. Only the ones listed on the credential are offered.
4. Click **Verify and continue**.

![The credential picker, grouping credentials under Access verified and Partial access](https://files.readme.io/740f5df07f1928ebeb87dae753536319d44a5e548a7f7e9c2369db4b0412b437-07-credential-picker.jpg)

![Step 1 with a credential, database and schema selected](https://files.readme.io/42789feb7bd3ec1daa42c874207e34e26d8efff9f3e073bbbfb5eb8c2ca2e5a5-08-step1-credential-selected.jpg)

### 2. Select tables

Pick the one table to sync. Each row shows the table's row count, column count, size and when it was last updated, and selecting a table lists its columns and their types on the right.

![Step 2, Select a table, with one table selected and its columns listed](https://files.readme.io/b9e0db397db276bf996f44ce8f371f828e325d14c34881d7287c8e4227151837-09-step2-select-table.jpg)

A few things to know about this list:

**Only tables and materialized views are listed.** Views, external tables and dynamic tables are not shown, even where access was granted.

**A table that is already connected cannot be picked again.** It is disabled and labelled **Connected via** followed by the name of the integration that already reads it, so the same rows are never counted twice.

**A table that has not been written to for more than 7 days shows a warning.** You can still connect it. If a scheduled job is meant to fill the table, check that the job still runs, because until it does every sync reads the same rows.

### 3. Data setup

Lifesight shows the row and column counts and a preview of the first rows, then asks two questions.

![Step 3, Data setup, with the date column, granularity and layout choices](https://files.readme.io/5aefe0497127c2b270c9cd12b118f37845d5a6a9e12ea5958e35493fa8ad6a75-10-step3-data-setup.jpg)

**Which column has the date?** Pick the date column and its granularity, such as Daily. Lifesight checks that the dates are consistent before ingesting.

**How is your data laid out?**

* **Stacked rows**: every row is one record, and sources or channels appear as values in a column.
* **Pivoted columns**: every row is one date, and each source or channel has its own column.

Below the two questions, a preview shows the first 15 rows of the table.

![The data preview on step 3, showing the first 15 rows](https://files.readme.io/e91839fcfcc25cfb111858cf068afc7b68c1de8f6fae661b039c3167dec09851-11-step3-preview.jpg)

### 4. Schedule & sync

**Frequency.** Choose how often Lifesight reads the table. Times are shown in your browser's local time zone. The first sync starts as soon as you connect, then repeats on this schedule.

| Frequency | What you set |
| :-- | :-- |
| Daily | The time of day. |
| Weekly | The day of the week and the time. |
| Monthly | The day of the month and the time. |
| Manual | Nothing. Data refreshes only when you sync from the integration page. |

![Step 4, Schedule, with frequency and time](https://files.readme.io/bedf8023fb83893e379b1a47b52d8211bb87f068439aee741d16e034a567c289-12-step4-schedule.jpg)

**Each time we refresh.** Choose what happens to the data Lifesight already has:

| Option | Matching rows | New rows | Other rows |
| :-- | :-- | :-- | :-- |
| Replace and append (recommended) | Replaced | Added | Kept |
| Full replace | Replaced | Added | Removed |

Use **Replace and append** when the table grows over time and occasionally corrects recent rows. Use **Full replace** when the table is always the complete, current picture.

![The two refresh options on step 4, Replace and append and Full replace](https://files.readme.io/7b6dbaab225cd77ea99a3d90efa664d30525ac5d7a170e06e50a6a81e9fb9a28-13-step4-refresh-options.jpg)

Rows are matched on the date column to begin with. After the first sync you set the source's real keys in Data Transformation.

Click **Connect** to finish.

## After connecting

A confirmation reads **Integration successful**, and you return to the Add Integration page. The first sync can take 24 to 48 hours to complete.

![The Integration successful confirmation](https://files.readme.io/d89c1bd15c250447cba1a381b8718310997b5a7465102f1101ed75d28ff64be7-14-integration-successful.jpg)

On **Data > Integrations**, the Snowflake row shows its status, who connected it and the time of its last sync. Expand the row to see each data source and when it last synced.

![The integrations list with the Snowflake row expanded](https://files.readme.io/4a1a04fa17e73d3db52fef0b03cf2ca976744531263fe55e30ab5e709bfe6568-15-integrations-list.jpg)

Next, open **Data > Data Transformation**, find the source in the list, map its columns to Lifesight fields, and set its keys.

To sync another table, add another Snowflake integration and pick the same credential. You do not need to run the setup script again, unless the new table sits in a database or schema the credential does not list yet, or you granted **One table** and the new table was not included.

***

## Changing a credential

On step 1 of the wizard, pick the credential and click **Edit**. The dialog lists the integrations that use it.

![The Edit credential dialog, with the account identifier locked and the sign-in shown read-only](https://files.readme.io/eb5c5fbb71871ea104fdf48af981d9dea7ca7f26af835d0a549959a40abd05b8-16-edit-credential.jpg)

**You can change** the credential's name, the warehouse, and the databases and schemas it lists. After adding a database or schema, open **Setup script**, copy it again, re-run it in Snowflake, then click **Test and save**.

**You cannot change the account identifier** once an integration reads through the credential. Create a new credential for another account.

**You cannot change how it signs in.** The user, role and key belong to the saved credential. Add a new credential to use another key.

**Removing a database or schema stops the integrations that read it.** Anything an integration reads is marked **In use**. If you remove it, Lifesight names the integrations that will stop refreshing before you save. Data already loaded stays, and the integration refreshes again once it is pointed at something the credential can read.

![The warning shown after removing a schema that an integration reads](https://files.readme.io/6865978a7a8ac634757050f2e7be9bad8d8ea9002acb5f85dd241727c192c53e-17-edit-credential-warning.jpg)

## Troubleshooting

| What you see | Likely cause | What to do |
| :-- | :-- | :-- |
| "We could not sign in to your account as LIFESIGHT yet" | The script has not been run, the public key was changed when pasting, or access has not applied yet. | Run the whole script, check `RSA_PUBLIC_KEY_FP` in `DESC USER LIFESIGHT` and that the public key has no line breaks, wait a minute, then test again. |
| "JWT token is invalid" in Snowflake | The public key was not applied, or it includes the `BEGIN`/`END PUBLIC KEY` lines or line breaks. | Copy the script again from Lifesight and re-run step 2 of the script without editing the key. |
| "Lifesight cannot read database…" or "…schema…" | The name is misspelled, or the role has no `USAGE` on it. Snowflake gives the same answer for both. | Check the name against Snowflake, run step 5 of the setup script, then **Test and save**. |
| "Object does not exist" in Snowflake | Missing `USAGE` on the database or schema, or a typo in the fully qualified table name. | Check steps 5 and 6 of the script. |
| "No active warehouse" | The warehouse in the script differs from the one on the credential. | Make both the same, then re-run the script. |
| Password conversion error in Snowflake | A `LIFESIGHT` user already existed with a password. | Run the `UNSET PASSWORD` statement in step 2 before `SET TYPE = SERVICE`. |
| A table you granted is not in the list | It is a view, an external table or a dynamic table, or it is in a schema the credential does not list. | Use a table or materialized view, or add the schema to the credential. |
| "Enter only the part before .snowflakecomputing.com" | The full URL was pasted as the account identifier. | Enter only the identifier, for example `acme-xy12345`. |
| "A credential with this name already exists" | Another credential in the workspace has the same name. | Pick the existing credential from the list, or use another name. |
| "The test could not run because of a problem on Lifesight's side" | Nothing is wrong with what you entered. | Try again in a minute. |
| "Something went wrong on our side while connecting Snowflake" | Nothing is wrong with your account or permissions. | Try again in a few minutes, or contact support and quote the reference shown in the message. |
| Sign-in fails only from Lifesight | A network policy is blocking Lifesight's IP. | Allow `35.206.86.230`. See [If your account restricts sign-in by IP](#if-your-account-restricts-sign-in-by-ip). |