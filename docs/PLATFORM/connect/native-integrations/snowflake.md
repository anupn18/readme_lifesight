---
title: Snowflake
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
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
