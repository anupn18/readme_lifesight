---
title: Custom Rules
excerpt: >-
  Create rules to classify and simplify campaigns and Ads in the Attribution
  breakdown tab
deprecated: false
hidden: false
metadata:
  robots: index
---
Custom Rules are a powerful feature within the Lifesight UMM Platform that allow you to organize and analyze your marketing efforts with greater flexibility. They are utilized in the attribution breakdown tab to group campaigns, ad sets, and ads under a single, meaningful label. This enables you to see aggregated attribution metrics and receive recommendations specifically for these custom groups.

For example, you can create a rule to group all campaigns related to your "Summer Sale" under one label, even if they are running on different platforms with different naming conventions.

### Why Use Custom Rules?

Setting up custom rules provides several key benefits:

* **Simplified Reporting**: Condense hundreds of campaigns into clean, logical groups for easier analysis.
* **Consistent Naming**: Standardize your campaign taxonomy across different ad platforms by mapping them to unified labels.
* **Targeted Insights**: Generate attribution metrics and optimization recommendations for specific strategies, products, or regions.
* **Flexible Analysis**: Quickly pivot your attribution view to analyze performance by marketing objective, promotional event, or any other business logic.

### Creating a New Custom Rule

Follow these steps to build a new rule from scratch.

1. From the navigation menu, go to **Configurations**.
2. Select the **Rules & Labels** tab.
3. Click the **Create Rule** button in the top-right corner.
4. **Set the Primary Action**: At the top of the page, select the primary entity you want to assign a new value to from the **Action** dropdown. Options include `Assign to Channel`, `Assign to Objective`, and more.
5. **Define Rule Conditions**: In the **Rule 1** block, build the logic that will identify your target campaigns, ad sets, or ads.
   * **Source**: Select the data field you want to evaluate, such as `UTM Source`, `Campaign Name`, or `Objective`.
   * **Condition**: Choose the matching logic, like `Contains` or `equals`.
   * **Value**: Enter the text or value to match against (e.g., `search`, `google`).
   * To add more complexity, use the **AND** / **OR** dropdown to add another line of conditions.
6. **Set the Output Action**: Once the conditions are set, define the new label to be applied.
   * In the **Action** section, select `Label as`.
   * In the **Value** field, enter the new label you want to assign (e.g., `Google - Search`).
   * Optionally, select an **Icon** to associate with the new label.

![Screenshot of the rule creation interface in Lifesight, showing fields for Source, Condition, Value, and Action.](https://storage.googleapis.com/path/to/your/image/Rules%20&%20Labels%20-%20Prefilled%20Rule.jpg)

7. **Add More Rule Blocks (Optional)**: You can click `[Add Rule]` to create another block (e.g., **Rule 2**). This allows you to build a comprehensive set of mappings within a single configuration. For example, Rule 1 can handle Google Search, while Rule 2 handles Facebook Ads.

### Previewing Your Rule

Before saving, you can verify that your rule works as expected. The **Preview** table at the bottom of the page shows a real-time list of all campaigns, ad sets, and ads that are affected by your rule logic.

* The **Status** column will show a green **Matched** tag for any item that meets the conditions you defined.
* Use the **Filter** button to search for specific campaigns or ads to ensure they are being labeled correctly.

![Screenshot of the Preview table, showing a list of campaigns with a "Matched" status.](https://storage.googleapis.com/path/to/your/image/Rules%20&%20Labels%20-%20Rule%20preview.jpg)

<br />

### Saving Your Rule

Once you are satisfied with the preview, click the **Update Rule** or **Create Rule** button at the top of the page to save your configuration. Your new labels will now be applied to your attribution data.

<br />

### Managing Existing Rules

The **Rules & Labels** tab displays all the custom rules you have created. From here, you can monitor and manage them.

* **View Rules**: The main table lists each rule's name, the level it applies to (e.g., Account, Campaigns), and when it was last modified.
* **Activate/Deactivate**: Use the **Active** toggle next to a rule to turn it on or off. Deactivated rules will not be applied to your attribution data but are saved for future use.
* **Edit a Rule**: Click on a rule's name to open the editor and modify its conditions or actions.
* **Delete a Rule**: Click the **trash can icon** to permanently delete a rule.

> **Warning:** Be careful when deleting a rule, as this action cannot be undone and will remove the associated labels from your historical attribution data.