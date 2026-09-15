---
title: 'Automated deployment of experiments '
excerpt: >-
  Lifesight supports the automated deployment of experiments to Meta or Google
  for scale-up and hold-out experiments. Once a hypothesis has been generated
  and market selection has been completed, the relevant campaigns for the
  channel or tactic are chosen. Based on the channel, the following actions are
  taken.
deprecated: false
hidden: false
metadata:
  robots: index
---
This system ensures robust, fault-tolerant execution of geo experiments across Meta and Google. It automates the complex processes of entity duplication, targeting modification, budget redistribution, and synchronized activation while maintaining full visibility, tracking, and recovery through comprehensive logging and data storage.

## Meta

### Scale-up Experiments

Scale-up experiments in Meta Ads involve duplicating selected campaigns and increasing budget allocations exclusively for specific test markets, while modifying geo-targeting rules to isolate test and control groups. The process is as follows:

1. **Identify Campaign Type (CBO vs. ABO)**: The system first determines if a campaign is using Campaign Budget Optimization (CBO) or Adset Budget Optimization (ABO).

2. **Duplicate Campaigns**: Campaigns are duplicated with the prefix "LS-Exp" and set to PAUSED status. New campaigns inherit start and end dates matching the experiment duration.

3. **Budget Allocation**:

   * Calculate total budget across selected campaigns and ad sets.
   * Determine each campaign's (CBO) or ad set’s (ABO) share of the total.
   * Multiply each share by the experiment investment to derive the new budget.
   * For CBO: Apply the calculated budget at the campaign level.
   * For ABO: Distribute the campaign’s allocated budget across ad sets proportionally.

4. **Adset and Ad Duplication**: All adsets and ads are duplicated with modified geo-targeting. For ABO, budget is set at the adset level. For CBO, targeting is retained but budgets are centralized.

5. **Geo Targeting**: Test markets are added to duplicated adsets. Original adsets are updated to exclude test markets during the test period.

6. **Synchronized Test Start and End**:

   * At test start: Activate duplicated campaigns, adsets, and ads. Apply exclusions to original adsets.
   * At test end: Pause duplicates and remove exclusions from originals.

7. **Logging & Rollback**:
   * All actions are logged with success/failure status.
   * Original budget values and targeting settings are stored for restoration.

<br />

### Hold-out Experiments

Hold-out experiments in Meta involve excluding test markets from existing campaigns to measure incremental lift. The process includes:

1. **Fetch Geo-Level Spend**: Retrieve campaign-level spend broken down by geo (country, region, city) to calculate test/control market distribution.

2. **Determine Budget Optimization Type**: Classify each campaign as CBO or ABO and group by budget type (daily or lifetime).

3. **Budget Adjustment Logic**:\
   After calculating new budgets for each campaign or ad set, the system classifies the scenario into one of the following cases:

   * **Case 1 – Investment exceeds test market spend**:

     * The system identifies surplus investment after removing the test market spend.
     * It estimates how much of this would have naturally reallocated to control markets.
     * If the surplus is smaller than this natural shift (**Case 1A**), budgets are reduced to avoid overspend.
     * If the surplus is greater than the natural shift (**Case 1B**), budgets are increased to absorb the extra investment across control markets.

   * **Case 2 – Investment is less than test market spend**:

     * Budgets are reduced by the proportion of spend removed, without any increase elsewhere.

   * For lifetime budgets, adjustments are applied only to the remaining unspent portion.

4. **Launch Actions**:

   * Apply geo exclusions at the ad set level.
   * Update campaign and ad set budgets according to calculated adjustments.

5. **End Actions**:

   * Remove geo exclusions.
   * Restore original budget values.

6. **Logging & Rollback**:
   * All actions are logged with success/failure status.
   * Original budget values and targeting settings are stored for restoration.

<br />

<br />

## Google

### Scale-up Experiments

Scale-up experiments on Google Ads recreate campaigns to target test markets and allocate additional budget for performance uplift. The high-level process:

1. **Campaign Retrieval & Budget Calculation**:

   * Retrieve campaign metadata, budgets, assets, and geo-level spend.
   * Calculate the share of each selected campaign's budget relative to the total.
   * Distribute the experiment investment proportionally across selected campaigns only.

2. **Campaign Duplication**:

   * Create new budget IDs with scaled budgets.
   * Duplicate campaigns and assets.
   * Apply geo targeting to test markets only.

3. **Ad Group & Ad Duplication**:

   * Replicate all ad groups and ads under duplicated campaigns.

4. **Launch Actions**:

   * At test start: Add geo exclusions to original campaigns; activate duplicates.
   * At test end: Pause duplicates; remove geo exclusions from originals.

5. **Advanced Budget Scaling**:

   * For each duplicated campaign, adjust the budget to include uplift for past underdelivery.
   * For each original campaign, subtract test market allocation to avoid double-counting.

6. **Logging & Rollback**:

   * All actions are logged with success/failure status.
   * Original budget values and targeting settings are stored for restoration.

### Hold-out Experiments

Hold-out tests exclude test markets from live campaigns to estimate geo-lift. The automation process includes:

1. **Geo Spend Analysis**: Fetch historical geo spend from geographic\_view using specified geo granularity.

2. **Budget Classification & Grouping**:

   * Group campaigns into shared vs. individual budgets.
   * Categorize by lifetime vs. daily budget.

3. **Budget Adjustment Logic**:\
   After calculating new budgets for each campaign, the system applies one of the following cases:

   * **Case 1 – Investment exceeds test market spend**:

     * The system identifies excess budget after test market exclusions.
     * It estimates the natural redistribution that would have occurred to control markets.
     * If the surplus is less than this natural shift (**Case 1A**), budgets are reduced to maintain parity.
     * If the surplus exceeds the natural shift (**Case 1B**), budgets are increased across control markets.

   * **Case 2 – Investment is less than test market spend**:

     * Budgets are reduced proportionally to the test market allocation without increasing others.

   * Lifetime budgets are adjusted based only on the unspent portion.

4. **Launch Phase**:

   * Apply campaign-level and ad group-level geo exclusions.
   * Update individual and shared budgets using calculated values.

5. **End Phase**:

   * Remove geo exclusions.
   * Restore original budgets from stored snapshots.

6. **Platform Constraints & Logging**:

   * Daily/lifetime budget thresholds are enforced.
   * All actions are logged to a datastore for monitoring and rollback.

Additional capabilities:

* **Uplift Logic**: Scale test campaign budgets based on underdelivery during the pre-test period.
* **Entity Mapping**: Source-destination mappings are recorded at every hierarchy level: Campaign → Ad Set → Ad.
* **Scheduling & Sync**: Automated start and end actions for all experiments ensure synchronized targeting and budget updates.