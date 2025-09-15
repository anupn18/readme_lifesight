---
title: Recommendations
deprecated: false
hidden: true
metadata:
  robots: index
---
The Optimizer is your **single control center for campaign budgets across channels**. Instead of logging into Google, Meta, YouTube, or TikTok separately, you can review, adjust, and apply all your campaign recommendations in one place.

Once you set a scenario as your **Default Scenario**, the system automatically generates recommendations that align your live campaigns with your strategic plan. These recommendations appear in the **Optimizer Table**, where you can:

* Instantly see which campaigns should be scaled, reduced, or maintained.
* Compare current vs recommended budgets at a glance.
* Edit budgets, bid targets, or campaign statuses directly in-line.
* Apply updates across multiple campaigns and channels with a single confirmation.

This makes the Optimizer not just an analysis tool, but an **execution layer** — connecting your MMM plan directly to campaign management.

### How Recommendations Are Generated

* **Default Scenario as source of truth**: Recommendations are only generated for the **Default Scenario**. This ensures there’s a single, consistent baseline for optimization.
* **Entity-level recommendations**: The Optimizer breaks down scenario-level adjustments and distributes them across campaigns and ad sets, factoring in past spend, performance, and eligibility.
* **Platform compliance**: Every recommendation respects the rules of the ad platform (e.g., Target CPA values can only be updated if the campaign uses a Target CPA bidding strategy).

### The Optimizer Table

All recommendations are visible in the **Optimizer Table**.

Each row shows:

* **Entity Name** – Campaign or ad set name.
* **Recommendation** – Badge showing “Scale Budget by X%,” “Reduce,” or “Maintain.”
* **Recommended Budget** – Editable suggested budget value.
* **Budget Setting** – Whether it’s Daily or Lifetime, and if it’s CBO or ABO.
* **Current Budget / Spend** – Reference values pulled from the ad platform.
* **Bid Strategy & Target** – Current bidding strategy; bid target editable when supported.
* **Status** – Current campaign/ad set status (enabled or paused).
* **Warnings** – Inline risk flags (e.g., “Campaign ends soon” or “Low conversions”).

> 📘 _Tip:_ Campaigns using shared budgets appear as separate rows, but edits apply once at the shared budget level.

### Acting on Recommendations

Only **Managers and Admins** of a workspace can edit or apply recommendations.

You can act on recommendations in three ways:

1. **Edit Recommended Values**
   * Click the ✏️ (pencil) icon to override the suggested budget.
   * Adjust **bid target values** when supported by the campaign’s strategy.
   * This flexibility allows you to apply Optimizer recommendations as-is, or fine-tune them to reflect context outside the model.
2. **Pause Campaigns**
   * Directly change the campaign or ad set status (e.g., pause underperformers) from the table.
3. **Apply Recommendations**
   * Select one or more campaigns or ad sets.
   * Click **Apply** to open the **Confirmation Modal**, where you’ll see a final review:
     * Recommended vs current budgets
     * Warnings and risk flags
     * Shared budget awareness notes
   * Confirm to push changes live across your ad platforms.

Once applied, changes are executed in real time and tracked in the **Logs tab**, so you always have a full record of what changed, when, and by whom.

### Recommendation Lifecycle

* **Pending** – Recommendations are generated and awaiting your review.
* **Optimizing** – You’ve applied them, and the updates are being processed live.
* **Applied** – The changes have been successfully pushed to the ad platform.
