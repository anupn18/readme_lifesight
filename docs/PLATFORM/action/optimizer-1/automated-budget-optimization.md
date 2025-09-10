---
title: '[WIP] Automated Budget Optimization'
deprecated: false
hidden: true
metadata:
  robots: index
---
The Optimizer bridges the gap between strategic planning and tactical execution on your ad platforms. It translates your high-level budget scenarios into automated, gradual budget adjustments that are progressively rolled out to your campaigns. This progressive approach is designed to safely modify campaign budgets, preventing disruption to ad platform algorithms and avoiding the costly 'learning phase,' ensuring you can efficiently allocate your budget for maximum impact.

### How Recommendations are Calculated

The Optimizer's intelligence is directly linked to the scenarios you build in the Planner. It takes the channel-level spend allocation computed by a budget scenario and translates it into granular, daily or weekly budget modifications for individual campaigns and ad sets.

This translation from a high-level channel budget to a specific campaign budget is managed by Lifesight's proprietary allocation score, which considers historical performance and other factors to determine the most effective distribution of funds.

<br />

> 📘 Default Scenarios Only
>
> Please note that the Optimizer can only implement recommendations from a budget scenario that has been set as the 'default' in the Planner. This ensures that you are always acting on your primary, approved strategic plan.

<br />

### Configuring Guardrails

To ensure campaign stability and provide you with full control over automated changes, the Optimizer includes several configurable guardrails. These settings prevent drastic budget shifts that could disrupt the learning phase of your campaigns on ad platforms.

**Progressive Rollout**: Instead of applying large budget changes at once, the Optimizer rolls them out progressively through smaller daily or weekly adjustments. This gradual approach helps ad platform algorithms adapt without re-entering the volatile "learning mode."

**Budget Caps**: You can set maximum budget limits for campaigns to ensure spend never exceeds a predefined threshold.

**Budget Delta Limits:** This setting controls the maximum percentage a budget can be changed in a single adjustment, preventing unexpectedly large increases or decreases.

These guardrails can be configured in the Configuration settings page.

### Implementing Budget Recommendations

Once you have reviewed the recommendations and are ready to proceed, you can apply them directly from the Optimizer.

1. Navigate to Action > Optimizer from the left-hand menu.
2. Review the budget recommendations in the Channel Breakdown table. You can expand each channel to see campaign and ad-set level suggestions.
3. Click the pencil icon ✏️ at the top right of the table to enable selection mode. The checkboxes next to each campaign/ad set will become active.
4. Use the checkboxes to select the specific campaigns or ad sets you wish to optimize.
5. After making your selections, click the Apply button located at the bottom right of the screen.

<br />

### Final Confirmation (Budget Summary)

After you click Apply, a Budget Summary dialog box will appear. This is your final confirmation step before the changes are pushed to your ad platforms.

This summary provides a final overview of the changes to be implemented, including:

Overall Impact: Metrics like the change in Expected Spend and the Projected Change percentage.

Detailed Breakdown: A list of all selected campaigns and ad sets, showing the specific change from the Current Value to the New Value.

Review Carefully

Any changes confirmed on this screen will be automatically applied to the selected campaigns on your live ad platforms. Please review your changes carefully before proceeding.

Once you have verified the details, click Optimize to start the automated budget adjustments.
