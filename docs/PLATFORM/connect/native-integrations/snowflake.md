---
title: '[WIP] Snowflake'
excerpt: Integrate Snowflake to pull in Marketing data from your data warehouse
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
**Snowflake** is a fully managed cloud data platform that provides scalable storage, processing, and analysis for both structured and semi-structured data. It is widely used by data teams for its powerful query performance, elasticity, and ability to seamlessly operate across multiple cloud environments.

The **Lifesight–Snowflake** integration enables you to connect your Snowflake account to the Lifesight platform. Once connected, Lifesight can securely ingest your selected tables or views from Snowflake and unify them with your other marketing and business data sources. This integration allows for comprehensive attribution, analytics, and measurement within the Lifesight ecosystem.

<br />

Before setting up the integration, ensure the following prerequisites are met:

Snowflake Account Access: You have access to a Snowflake account with permission to create and manage integrations or external connections.

Warehouse and Database: Ensure that the datasets you want to connect are available in an active Snowflake warehouse and database.

Read Permissions: The user or service account used for integration should have at least SELECT privileges on the specific tables or views you plan to ingest.

Network Access: The Snowflake instance should be accessible from external connections. If IP whitelisting is enabled, ensure that Lifesight’s IP addresses are added to the allowed list.

Credentials: You’ll need your Snowflake account name, warehouse name, database, schema, username, and password or key-pair authentication details to complete the connection setup.

# Steps to Integrate with Snowflake

* In your Snowflake account, Go to `+` and click on `SQL Worksheet`
* Once done, paste the following in a New SQL Worksheet

```
-- Create a New User for Lifesight

CREATE USER Lifesight
  PASSWORD = 'Lifesight_Snowflake%000'  
  MUST_CHANGE_PASSWORD = FALSE  
  COMMENT = 'Lifesight User for access to Snowflake';  -- Optional, for documentation purposes


-- Create a new role

USE ROLE ACCOUNTADMIN;

CREATE ROLE LS_ADMIN;

-- Assign permissions to access the database

GRANT USAGE ON DATABASE {{your_database_name}} TO ROLE LS_ADMIN;

-- If the database is imported, comment the above line and uncomment the following line

-- GRANT IMPORTED PRIVILEGES ON DATABASE {{your_database_name}} TO ROLE LS_ADMIN;

-- Grant permission to access the schema

GRANT USAGE ON SCHEMA {{your_database_name}}.{{schema_name}} TO ROLE LS_ADMIN;

-- Grant permission to access the table
 
GRANT SELECT ON TABLE {{your_database_name}}.{{schema_name}}.{{your_table_name}} TO ROLE LS_ADMIN;


-- Grant the created role to the created Lifesight user:

GRANT ROLE LS_ADMIN TO USER Lifesight;

--Set Default Role to the created Lifesight user to be LS_ADMIN:

ALTER USER Lifesight SET DEFAULT_ROLE = "LS_ADMIN";
```

* Execute all the commands in the above worksheet
* Provide Lifesight with the following information to complete the integration:
  * Database Name
  * Schema Name
  * Table Name
  * Region
* Lifesight support will reach out to you once the integration is ready
