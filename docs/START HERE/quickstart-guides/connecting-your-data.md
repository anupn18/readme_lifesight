---
title: Connecting your data
excerpt: Fast path using top connectors or CSV templates; verification checks.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Connecting Your Data

Connect your core marketing and outcome data in 30–60 minutes using native connectors or CSV templates, then run light verification so your first Measure read is trustworthy.

## Overview

*   **Audience:** Performance & Media, Analytics & Insights, Marketing Ops
*   **Goal:** Get the minimum viable dataset into Lifesight to enable your first incrementality read and scenario planning
*   **Time:** 30–60 minutes
*   **Prerequisites:** Admin access to ad platforms/analytics/ecommerce; agreed UTM/taxonomy; workspace owner role
*   **Outcomes:** Connectors authenticated or CSV files uploaded; data mapped; verification checks passed; refresh schedule set

## At a Glance: Minimum Viable Data to Start

*   **Outcomes:** Orders/Revenue (daily or weekly), New vs Returning if available
*   **Media:** Channel‑level spend (and impressions if available) for active paid channels
*   **Context:** Seasonality/holiday calendar; promo flags if available

### Better Data Considerations

*   Geo splits (DMA/State/Region)
*   Price & promo calendar
*   High‑level creative/audience tags
*   Retail/POS rollups

### Common Connectors

*   **Commerce/Analytics:** Shopify, GA4
*   **Ads:** Meta Ads, Google Ads (incl. YouTube), TikTok Ads, Snapchat, CTV/retail media partners
*   **Warehouses/Storage:** BigQuery, Snowflake, S3/GCS
*   **Privacy:** Works on aggregated/pseudonymized data; no dependence on third‑party cookies

## Choose Your Path

### Path A — Connectors (Recommended)

Use native connectors to pull clean, auto‑refreshed data.

#### Step A1 — Select and Authenticate Connectors

*   **Commerce/analytics (at least one):** Shopify and/or GA4
*   **Paid media (2+ channels):** Meta Ads, Google Ads/YouTube, TikTok Ads, plus any others you actively spend on
*   **Optional:** Warehouse (BigQuery/Snowflake) if finance or offline data will be joined
*   Authenticate with the least‑privilege scopes (read‑only where possible)

#### Step A2 — Select Accounts and Properties

*   Confirm you’re connecting the right ad accounts, GA4 properties, and storefronts
*   Set currency, timezone, and fiscal week alignment for the workspace

#### Step A3 — Map Fields and Taxonomy

*   Map channels to a standard taxonomy (e.g., Paid Social, Paid Search, Video/CTV, Affiliate, Email)
*   Confirm UTM conventions and configure Rules & Labels for consistent campaign naming
*   If using multiple storefronts/regions, map to your Geo dimension

#### Step A4 — Initial Backfill

*   Pull at least 3–6 months of history (12–24 months is ideal and can continue in the background)
*   Confirm the date boundaries per connector (UTC vs local time)

### Path B — CSV Templates (Fastest Fallback)

If a connector isn’t available or you want to start today, upload CSVs using the templates.

#### Step B1 — Download Templates

*   **Outcomes template:** date, region (optional), orders, revenue, new_vs_returning (optional)
*   **Media template:** date, channel, campaign_name (optional), spend, impressions (optional), clicks (optional)
*   **Context template (optional):** date, promo_flag, holiday_name, price_index (if applicable)

#### Step B2 — Populate and Validate

*   One row per date (and region if used), UTF‑8 CSV, headers intact
*   Use ISO dates (YYYY‑MM‑DD) and a single currency across files
*   Keep channel names consistent with your taxonomy (e.g., “Paid Social”, “Paid Search”, “CTV”)

#### Step B3 — Upload and Map

*   Upload each file to its designated template
*   Map columns to the expected fields and confirm data types (numeric vs text)
*   If you include regions, ensure region names match a single standard (e.g., “CA” not “California”)

## Verify Your Connection (10–15 minutes)

Run these sanity checks before moving on:

### Check 1 — Volume Parity (Last 7–14 Days)

*   **Revenue/orders:** Within ±2–5% of your ecommerce source
*   **Spend:** Each connected platform within ±1–2% of its native UI for the same date range
*   **Impressions/clicks (if available):** Directionally aligned (±5–10%)

### Check 2 — Coverage & Recency

*   At least 2 active paid channels connected or represented in CSVs
*   Data freshness: Latest full day is present; scheduled refresh is confirmed

### Check 3 — Taxonomy & Mapping

*   Channels consistently mapped (no duplicates like “Facebook” and “Meta” as separate channels)
*   UTM keys or Rules & Labels categorize campaigns as expected (brand vs non‑brand, prospecting vs retargeting)

### Check 4 — Calendars & Currency

*   Workspace timezone and currency match your source of truth
*   Holiday/promo flags appear on expected dates

### Pass Criteria

If all checks pass, you’re ready for your first Measure read.

## Set Refresh & Governance

*   **Refresh cadence:** Daily pull for ads/analytics; weekly or daily for commerce outcomes
*   **Owner & backups:** Assign a data owner and a secondary contact
*   **Access control:** Workspace roles with least privilege; service accounts where supported
*   **PII policy:** Avoid exporting or uploading unnecessary personal data; keep datasets aggregate when possible
*   **Change management:** Document connected accounts, scopes, and any transformation rules

## Common Pitfalls (and Quick Fixes)

*   **Authentication errors / missing permissions**
    *   **Fix:** Re‑authenticate with the correct scopes; confirm you have access to the intended accounts/properties.
*   **Timezone/currency mismatches**
    *   **Fix:** Align workspace timezone/currency with your finance/ecommerce system; re‑ingest if needed.
*   **Double counting channels**
    *   **Fix:** Standardize channel mapping; use Rules & Labels to merge “Facebook/Meta” into “Paid Social”.
*   **Gaps in history**
    *   **Fix:** Increase backfill window per connector; for CSVs, add the missing date range and re‑upload.
*   **Spiky or zero values**
    *   **Fix:** Confirm platform outages/promotions on those dates; re‑pull data; check for header or delimiter issues in CSVs.

## Definition of Done

*   Required connectors authenticated or CSVs uploaded and mapped
*   Last 7–14 days validated for volume, coverage, and recency
*   Workspace settings (timezone, currency, fiscal calendar) confirmed
*   Refresh cadence and ownership defined

Once complete, proceed to your first incrementality read.

## What Happens Next

*   Run your first Measure read: See contribution and marginal effects across channels
*   Launch a priority geo test: Prove lift for a debated channel/tactic
*   Calibrate attribution: Apply incrementality factors so daily KPIs align with causal truth
*   Build a forecast & plan: Use scenarios and constraints to reallocate budget

### Read Next

*   Quickstart: Run your first Measure read
*   Quickstart: Launch a geo‑lift test
*   Quickstart: Calibrate attribution with incrementality
*   Quickstart: Build a forecast & plan
*   What Data Do I Need for Lifesight?