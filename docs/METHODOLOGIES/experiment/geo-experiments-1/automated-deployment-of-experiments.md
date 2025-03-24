---
title: 'Automated deployment of experiments '
excerpt: >-
  Lifesight supports the automated deployment of experiments to Meta or Google
  for scale-up and hold-out experiments. Once a hypothesis has been generated
  and market selection has been completed, the relevant campaigns for the
  channel or tactic are chosen. Based on the channel, the following actions are
  taken.
deprecated: false
hidden: true
metadata:
  robots: index
---
## Meta

### Scale-up Experiments

Scale-up experiments involve duplicating existing campaigns and increasing budgets for specific test markets. The process includes:

1. **Determining Campaign Budget Optimization Type**: The system first identifies whether the campaign uses Campaign Budget Optimization (CBO) or Adset Budget Optimization (ABO).

2. **Creating Duplicate Campaigns**: Original campaigns are duplicated with the prefix "LS-Exp" and set to PAUSED status initially.

3. **Budget Allocation**: For CBO campaigns, budgets are adjusted at the campaign level. For ABO campaigns, each ad set's budget is modified according to the experiment requirements.

4. **Geo-Targeting Modification**: The duplicate campaigns target only the test markets, while the original campaigns exclude those markets during the test period.

5. **Synchronized Launch and End**: At the test start date, the original campaigns exclude test markets and the duplicate campaigns are activated. At the end date, all changes are reverted.

### Hold-out Experiments

Hold-out experiments involve excluding specific markets from existing campaigns. The process includes:

1. **Fetching Geo-Based Spend Data**: The system retrieves historical spend data broken down by geo-location to understand current investment distribution.

2. **Budget Calculation and Adjustment**: Based on the desired investment level, the system calculates necessary budget adjustments to maintain balanced investment across test and control markets.

3. **Updating Ad Set Targeting**: The system adds geo-location exclusions to prevent ads from showing in test markets.

4. **Budget Distribution**:
   * If the investment is greater than test market spend, the system may increase or decrease budgets depending on the net budget adjustment.
   * If the investment is less than test market spend, the system simply removes the test market portion from each campaign/ad set budget.

5. **End Phase Restoration**: At the test end date, all geo-targeting exclusions are removed, and original budget amounts are restored.

## Google

### Scale-up Experiments

Google scale-up experiments recreate campaigns for test markets, with adaptations specific to the Google Ads platform:

1. **Authentication and Campaign Retrieval**: The system authenticates and retrieves detailed information about the selected campaigns, their assets, and criteria.

2. **Budget Allocation Calculation**:
   * Calculate total budget across all original campaigns
   * Calculate ratio of each campaign's budget to total budget
   * Apply these ratios to the experiment investment to determine new test budgets
   For example:
   * Original Campaigns: Campaign A ($100/day), Campaign B ($50/day), Campaign C ($50/day)
   * Total Original Budget: $200/day
   * Experiment Investment: $600/day
   * Budget Allocation:
     * Campaign A: ($100/$200) × $600 = $300/day
     * Campaign B: ($50/$200) × $600 = $150/day
     * Campaign C: ($50/$200) × $600 = $150/day

3. **Campaign Duplication**:
   * Create new budget ID for each campaign with calculated budget allocation
   * Create new campaign with the new budget
   * Copy non-location campaign criteria
   * Copy campaign assets
   * Add test markets in targeting to duplicated campaign

4. **Ad Group Duplication**: For each ad group in the original campaign, create a corresponding ad group in the duplicated campaign, copying all relevant settings and assets.

5. **Ad Duplication**: Copy all ads under each ad group to the corresponding duplicated ad group.

6. **Synchronized Launch and End**:
   * At test start: Add location exclusions to original campaigns and activate duplicate campaigns
   * At test end: Pause duplicate campaigns and remove location exclusions from original campaigns

### Hold-out Experiments

Google hold-out experiments involve:

1. **Fetching Geo-Based Spend Data**: The system retrieves historical spend data for campaigns by geo locations to understand investment distribution between test and control markets.

2. **Budget Calculation**:
   * Group campaigns by shared budgets vs. individual budgets
   * Calculate budget adjustments based on three cases:
     * Case 1A: When investment > test market spend, but extra investment \< natural redistribution (budget reduction)
     * Case 1B: When investment > test market spend and extra investment > natural redistribution (budget increase)
     * Case 2: When investment \< test market spend (simple test market proportion removal)
   * Handle shared budgets and partially spent lifetime budgets appropriately

3. **Launch Actions**:
   * Add campaign-level and ad group-level location exclusions for test markets
   * Update campaign budgets for individual campaigns
   * Update shared campaign budgets

4. **End Actions**:
   * Remove all location exclusions
   * Restore original budget amounts for both individual and shared campaign budgets

## Technical Implementation

The system uses the respective advertising platforms' APIs to implement these changes:

* **Meta Graph API**: For campaign duplication, budget adjustments, and targeting modifications.
* **Google Ads API**: For campaign recreation, budget management, and geo-targeting exclusions.

All modifications are tracked in the system for monitoring, insights, and cleanup purposes. The system includes error handling, retries, and rollback mechanisms to ensure reliable experiment execution.