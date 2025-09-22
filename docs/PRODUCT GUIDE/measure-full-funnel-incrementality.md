---
title: Measure
excerpt: >-
  How to measure full-funnel marketing effectiveness using multiple
  methodologies
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
# Measure: Full-Funnel Marketing Effectiveness

Measure provides a unified, causally correct view of marketing impact—from brand to performance—to identify incremental contributions, optimal marginal returns, and inform channel scaling, capping, or testing strategies.

## At a Glance

*   **Purpose:** Replaces conflicting platform numbers with a causal read of incremental contribution and marginal returns (mROAS).
*   **Who it's for:** CMO/VP Growth, CFO/FP&A, Performance & Media, Analytics & Insights.
*   **Decisions you’ll make:**
    *   Where to allocate the next dollar (scale vs. cap).
    *   Which channels/tactics require geo tests to prove lift.
    *   What guardrails to implement (retargeting/brand search caps, prospecting floors).
*   **Primary outputs:**
    *   Baseline vs. incremental contribution by channel/tactic/geo.
    *   Marginal returns curves and saturation thresholds.
    *   Uncertainty bands and readiness flags.
    *   Shareable executive read-outs for finance and leadership.
*   **Works with:** Forecast (scenario planning), Optimize (daily guardrails), Analyze (dashboards), and Methodologies (MMM, Geo Tests, Calibrated Attribution).

## What Measure Includes

### Overview

A single page answering: “How much was incremental vs baseline?” and “What should we do next?”

*   Baseline vs media contribution.
*   Top channels/tactics by incremental impact.
*   A guided Scale / Cap / Test shortlist.

### Channel & Tactic Contribution

*   Incremental revenue/orders and share by channel/tactic.
*   Optional splits for Brand vs Non-Brand (Search) and Prospecting vs Retargeting (Social/Programmatic).
*   Geo breakdowns (where available).

### Marginal Returns (Curves)

*   mROAS and saturation points for each channel/tactic.
*   “Add/Remove $” sliders to preview the impact of small budget moves.
*   Headroom indicators (how far until the next plateau).

### Uncertainty & Quality

*   Confidence ranges on contributions and curves.
*   Model/stability diagnostics and data coverage checks.
*   Flags for issues (flat spend, short windows, taxonomy drift).

### Read-out Builder

*   One-page executive summary (incremental vs baseline, top moves, risks).
*   Finance view (profit/payback alignment, ranges).
*   Links to Forecast for “what-if” and to Optimize for guardrails.

## How Measure Works (High-Level)

*   **Causal MMM:** Estimates baseline demand vs. media impact, incorporating lag/decay and saturation.
*   **Geo-based Incrementality Tests:** Calibrate ambiguous channels (e.g., CTV/YouTube, retargeting, brand search) with measured lift.
*   **Incrementality-calibrated Attribution:** Aligns daily, granular KPIs to causal truth for operations.

This results in a triangulated view explainable to both marketing and finance.

**Deep dives:** [Causal MMM](_PLACEHOLDER_LINK_TO_CAUSAL_MMM_) · [Geo-based Incrementality Testing](_PLACEHOLDER_LINK_TO_GEO_TESTING_) · [Incrementality-calibrated Attribution](_PLACEHOLDER_LINK_TO_CALIBRATED_ATTRIBUTION_)

## Typical Workflows

### Baseline → Actions (First 60–90 minutes)

*   Run a baseline read (weekly aggregation recommended).
*   Map channel splits (Brand/Non-Brand, Prospecting/Retargeting).
*   Review marginal curves and create a Scale / Cap / Test list.
*   Share the read-out with finance and channel leads.

See [Quickstart: Run your first “Measure” read](_PLACEHOLDER_LINK_TO_QUICKSTART_)

### Monthly Cadence

*   Refresh the read with the latest data.
*   Convert changes in curves into scenario candidates in Forecast.
*   Update Optimize guardrails (caps/floors, ramp limits) if curves or calibration shifted.

### After a Geo Test

*   Apply measured lift to calibrate both MMM and attribution.
*   Re-check curves for the tested channel; adjust caps/floors accordingly.
*   Note the updated uncertainty ranges and any new “scale” recommendations.

### Before/After Seasonal Windows

*   Ensure promo/price and seasonality are included as context variables.
*   Expect raw platform ROAS to spike; Measure will keep incrementality honest.

## Interpreting Measure Outputs

*   **Baseline vs Media:** The clean separation between demand you’d earn anyway (seasonality, price/promo, brand momentum) and incremental media.
*   **Channel Ranking:** Read by incremental contribution—not raw platform ROAS.
*   **Marginal vs Average:** Use mROAS to decide where the next dollar goes; iROAS (average) is descriptive, not prescriptive.
*   **Saturation:** Curves flatten as you near capacity—add dollars elsewhere once mROAS drops below your hurdle.
*   **Uncertainty:** Treat bands as risk bounds; pick actions that still make sense under the lower bound.

**Rule of thumb:** If lower-funnel (retargeting/brand search) dominates, test and cap; if upper-funnel curves are steep with headroom, scale.

## Decision Recipes (Ready to Use)

*   **Scale:** Channels/tactics with steep mROAS and room before saturation.
*   **Cap:** Tactics with flattening curves or proven over-credit (retargeting/brand search).
*   **Test:** High-spend + high-uncertainty areas (CTV/YouTube, prospecting, category retail) → launch geo tests.
*   **Rebalance:** Shift budget from flat regions to steep ones; enforce caps/floors in Optimize.

## Data Requirements & Mapping

### Minimum Viable

*   **Outcomes:** Orders/Revenue (weekly or daily), new vs returning if available.
*   **Media:** Channel-level spend (impressions helpful but optional) across ≥2 active channels.
*   **Context:** Seasonality/holiday flags; promo markers if used.

### Better

*   **Splits:** Brand vs Non-Brand, Prospecting vs Retargeting.
*   **Geo:** DMA/State/Region for both media and outcomes.
*   Retail/POS roll-ups (if omnichannel).
*   Price/promo intensity; product/inventory flags; creative/audience tags.

### Mapping Guidelines

*   Keep channel taxonomy tight (avoid “Facebook” vs “Meta” duplicates).
*   Use one currency, one timezone, and consistent ISO weeks.
*   Ensure outcome geo mapping (shipping/billing ZIP, store region) is stable across time.

See also: [What Data Do I Need for Lifesight?](_PLACEHOLDER_LINK_TO_DATA_REQUIREMENTS_) · [Connect your data (Quickstart)](_PLACEHOLDER_LINK_TO_CONNECT_DATA_)

## Governance, Refresh & Versioning

*   **Refresh cadence:** Quarterly as a baseline; monthly in high-change periods.
*   **Quality checks:** Coverage/recency, spend variation, seasonality/promo inclusion, geo consistency.
*   **Versioning:** Name runs (e.g., “Baseline – Q3 2025”), note assumptions and calibration status.
*   **Change log:** Record model updates, taxonomy changes, and test anchors used for calibration.

## Permissions & Roles (Suggested)

*   **Workspace Owner / Admin:** Configure data sources, fiscal settings, roles.
*   **Analytics & Insights:** Own data hygiene, modeling choices, calibration, and read-outs.
*   **Performance & Media:** Use outputs to set caps/floors and weekly optimizations.
*   **CFO/FP&A:** Review finance view (profit/payback), approve plan changes and guardrails.

## Exports & Hand-offs

*   Executive summary for leadership/finance (incremental vs baseline, top moves, risk notes).
*   Scenario hand-off to Forecast (curves + constraints) to compare Efficiency/Balanced/Growth options.
*   Guardrail hand-off to Optimize (caps/floors, ramp limits, target iROAS/iCAC).
*   Analyst workbook (filters, history compare) for deep dives in Analyze.

## Troubleshooting

*   **Everything looks flat:** Extend date range, add geo granularity, verify spend variation and promo flags.
*   **Lower-funnel looks “best”:** Classic over-credit—run geo holdouts and cap while you calibrate attribution.
*   **Wide uncertainty bands:** Aggregate thin tactics, extend history, or prioritize a test to add evidence.
*   **Results fight intuition:** Check taxonomy, currency/timezone, and seasonality/promo mapping; confirm there are no duplicate channels.

## FAQs

*   **How much history do we need?** More is better (12–24 months ideal), but you can start with 3–6 months if there’s variation—then tighten with geo tests.
*   **Weekly or daily?** Start weekly for stability; move to daily only once the baseline is trustworthy.
*   **Does Measure replace GA4 or platform dashboards?** No. We calibrate and reconcile them so daily KPIs reflect incrementality, then roll that truth up for planning.
*   **Can we include retail/POS?** Yes. Bring POS roll-ups mapped to geo; Measure will read total incremental impact and halo.
*   **How do we use the curves operationally?** Use Forecast to simulate changes with risk bands, and Optimize to enforce caps/floors that reflect the curves.

## What “Good” Looks Like

*   One causal truth accepted by marketing and finance.
*   A standing Scale / Cap / Test list tied to curves and uncertainty.
*   Prospecting floors and harvester caps enforced via Optimize.
*   Quarterly refresh with test-anchored calibration; monthly mini-re-plans as needed.
*   Fewer “whose numbers are right?” debates; faster budget decisions.

## Related Content

*   **Quickstart:** [Connect your data](_PLACEHOLDER_LINK_TO_CONNECT_DATA_) · [Run your first “Measure” read](_PLACEHOLDER_LINK_TO_RUN_FIRST_READ_) · [Launch a geo-lift test](_PLACEHOLDER_LINK_TO_LAUNCH_GEO_TEST_) · [Calibrate attribution with incrementality](_PLACEHOLDER_LINK_TO_CALIBRATE_ATTRIBUTION_)
*   **Methodology:** [Causal MMM](_PLACEHOLDER_LINK_TO_CAUSAL_MMM_DETAIL_) · [Geo-based Incrementality Testing](_PLACEHOLDER_LINK_TO_GEO_TESTING_DETAIL_) · [Incrementality-calibrated Attribution](_PLACEHOLDER_LINK_TO_CALIBRATED_ATTRIBUTION_DETAIL_)
*   **Outcome Playbooks:** [Prove Incremental ROI](_PLACEHOLDER_LINK_TO_PROVE_INCREMENTAL_ROI_) · [Maximize Media Efficiency](_PLACEHOLDER_LINK_TO_MAXIMIZE_MEDIA_EFFICIENCY_) · [Acquire New Customers Efficiently](_PLACEHOLDER_LINK_TO_ACQUIRE_NEW_CUSTOMERS_) · [Seasonality & Promotions](_PLACEHOLDER_LINK_TO_SEASONALITY_PROMOTIONS_)
*   **Product Guides:** [Forecast](_PLACEHOLDER_LINK_TO_FORECAST_GUIDE_) · [Optimize](_PLACEHOLDER_LINK_TO_OPTIMIZE_GUIDE_) · [Analyze](_PLACEHOLDER_LINK_TO_ANALYZE_GUIDE_)
