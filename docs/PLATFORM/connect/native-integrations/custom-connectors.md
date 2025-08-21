---
title: Custom Connector
excerpt: Connect any custom data sources using custom APIs and webhooks
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

The Custom Connector feature allows you to bring data from any external API or Webhook into the Lifesight Unified Marketing Measurement (UMM) platform. This enables you to integrate platforms and systems that are not available as pre-built Lifesight integrations.

With Custom Connectors, you can:

1. Configure APIs and Webhooks under a single connector.
2. Add multiple APIs and Webhooks for a single connector.
3. Reuse the same process to create new connectors for different platforms.
4. Change or update configurations at any time.
5. Trigger an on-demand fetch of data by clicking the Run (▶️ play) button.

This provides full flexibility to integrate your proprietary or third-party systems with Lifesight, ensuring complete visibility into your marketing and business data.

### Key Capabilities

**APIs & Webhooks Support**\
Add one or more API endpoints and/or Webhook URLs to fetch or receive data into Lifesight.

**Multiple Configurations per Connector**\
Each connector can hold multiple APIs and Webhooks simultaneously, giving you flexibility in managing data ingestion.

**Editable Configurations**\
Modify, update, or extend configurations whenever requirements change, without creating a new connector.

**Run on Demand**\
Once configured, click the Run (▶️) button to trigger immediate data fetch from the API.

**Scalable**\
To integrate another platform, simply repeat the connector creation process and set up new APIs/Webhooks.

<br />

## Quick start (at a glance)

1. **Create connector →** Name & describe it.
2. **Add API →** Define base URL, auth, an endpoint, and response mapping → **Test** → **Save**.
3. **(Optional) Add more APIs** to the same connector.
4. **Add Webhook →** Generate URL or paste the callback URL, set verification, map payload → **Test** → **Save**.
5. **Run (▶︎)** an API to fetch data and **verify** logs/preview.
6. **Publish/Enable** the connector for ongoing use.

***

## Detailed setup — Create a new Custom Connector

### 1. Start a new connector

<Image align="center" width="400px" src="https://files.readme.io/42ec03eafc2177afeeda606124d2dc811912f8a263167d165b2a7114ec774a98-image.png" />

1. Go to **Connectors** → **Custom Connector**.
2. Click **New Connector**.
3. Enter a **Connector Name** (e.g., “Support API + Webhooks”).
4. (Optional) Add a **Description** (purpose, data types, owners).
5. Click **Create** (or **Save**).

### 2) Configure authentication (connector-level or per endpoint)

Choose how the connector authenticates with your API provider. Common options:

* **No Auth** — public endpoints.
* **API Key (Header or Query)** — provide key and location (e.g., header `Authorization: Api-Key <key>` or query `?api_key=<key>`).
* **Bearer Token** — `Authorization: Bearer <token>`.
* **Basic Auth** — username/password.
* **OAuth 2.0** — provide client ID/secret, scopes, auth/token URLs; complete authorization.

> Tip: If authentication differs per endpoint, you can override it when defining an individual API.

### 3. Add your first API endpoint

1. In the connector, click **Add API**.
2. **General**
   * **Name** the endpoint (e.g., “List Tickets”).
   * **Base URL** (e.g., `https://api.example.com`), then set the **Path** (e.g., `/v1/tickets`).
   * **HTTP Method**: GET, POST, PUT, PATCH, DELETE.
   * (Optional) **Headers** and **Query Params** (e.g., `Accept: application/json`, `status=open`), and **Path Params** if needed.
3. **Authentication** (if not inherited)
   * Select the auth type for this endpoint and provide credentials.
4. **Request Body** (for POST/PUT/PATCH)
   * Choose content type (e.g., JSON) and define the body template. You can add variables and test values.
5. **Pagination** (if the API is paginated)
   * Choose the pagination mode: **Cursor/Token**, **Page/Per-Page**, or **Offset/Limit**.
   * Provide the **parameter names** and (if cursor) the **path** to the next token in the response.
6. **Rate Limiting** (optional)
   * Define requests/second or per minute; configure retries/backoff.
7. **Response Mapping**
   * Select **JSON** as the response type (if applicable).
   * Set the **root path** to the list/records array (e.g., `data.items`).
   * Map **fields** from the response to **output columns** (e.g., `id`, `title`, `created_at`, `status`).
   * (Optional) Cast types, parse timestamps, and flatten nested objects.
8. **Test**
   * Click **Test** to execute once. Review **HTTP status**, **sample payload**, and **mapped preview**.
   * Fix any mapping/auth issues and retest until green.
9. **Save** the API endpoint.

### 4) Add more APIs to the same connector (optional)

* Repeat **Add API** for additional endpoints (e.g., “Get Ticket by ID”, “List Users”, “List Comments”).
* Each endpoint can have its own method, path, params, pagination, and mapping.

### 5. Add a Webhook

1. Click **Add Webhook**.
2. **Webhook URL**
   * If Lifesight **generates a unique URL**, copy it and register it in your source system, or
   * If the UI expects **your callback URL**, paste it here (depending on your architecture).
3. **Verification / Signing** (recommended)
   * Choose verification type (e.g., secret token in header, HMAC signature, basic auth). Provide the **secret** or **public key**.
4. **Events** (optional)
   * Select which event types to accept (e.g., `ticket.created`, `ticket.updated`).
5. **Payload Mapping**
   * Provide a sample payload or use a captured event to map fields to output columns.
   * (Optional) Add filters to accept/ignore certain events.
6. **Test**
   * Use the provider’s **test delivery** (or send a curl request) to trigger a sample webhook.
   * Confirm the request is **received**, **validated**, and **mapped**.
7. **Save** the webhook.

### 6) Choose destination / output

* Pick the **dataset/table** or destination collection where API and webhook data will land.
* Confirm schemas for each mapped endpoint/webhook align with your analytics/modeling needs.

### 7. Run and verify

1. On any configured API endpoint, click **Run** (▶︎ play) to fetch data immediately.
2. Check the **Run Logs** and **Preview** to confirm records and field mappings.
3. If required, tweak **params/mappings**, re-**Run**, and validate again.

### 8) Enable & monitor

1. **Enable** the connector (and any schedules, if scheduling is available in your plan/tenant).
2. Use **Logs / History** to monitor status, volumes, and errors.
3. Re-**Run** on demand for ad-hoc fetches.

***

## Editing configurations later

* You can **change any configuration** at the connector, API, or webhook level (auth, paths, params, mappings, pagination, verification).
* After changes, use **Run** to re-fetch and validate.
* Changes take effect for subsequent runs and incoming webhooks.

***

## Examples

### Example A — GET with page/per-page pagination

* **Method**: GET
* **Path**: `/v1/tickets`
* **Query**: `page=1`, `per_page=100`, `status=open`
* **Pagination**: Page/Per-Page; next page = `page + 1` until response array is empty or `has_more=false`.
* **Mapping Root**: `data`
* **Fields**: `id`, `subject`, `created_at`, `status`, `assignee.id as assignee_id`

### Example B — GET with cursor pagination

* **Method**: GET
* **Path**: `/v1/events`
* **Query**: `limit=500`, `cursor={{cursor}}`
* **Pagination**: Cursor; next token path: `meta.next_cursor`
* **Mapping Root**: `events`

### Example C — POST with JSON body

* **Method**: POST
* **Path**: `/v1/search`
* **Headers**: `Content-Type: application/json`
* **Body**: `{ "query": "status:open created_at:>2025-01-01" }`
* **Mapping Root**: `results.items`