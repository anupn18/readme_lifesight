---
title: How to setup custom rules
excerpt: >-
  Create your own Rules to view your Attribution Dashboard based on your
  preferences.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
[block:embed]
{
  "url": "",
  "provider": "",
  "href": "",
  "typeOfEmbed": "youtube"
}
[/block]


<br />

***

<br />

## Steps to setup custom rules

1. Navigate to the "Settings" section on your workspace and click on the 'Rules and Labeling' Tab.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1db5cf42f3752a6284da5ead5b816fe787266a05adde81427cd06e54c033001f-rues.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


2. Click on `Create Rules` to begin setting up a new custom rule.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/30689ff99c04093c6eb28e870d3a77d428a6dc3e7c7b2046f978748bd37a7a94-cr.jpg",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


2. **Define the Action**: The first step in creating a rule is selecting the appropriate option based on where you want your rule to have an impact. You can choose from the following options:
   1. Channels
   2. Objective
   3. Campaigns
   4. Ad groups
   5. Ads
3. **Specify Conditions**: To tailor your rule precisely, you need to define conditions based on the following criteria:
4. **UTM Parameter**: Choose from Source, Medium, Campaign and Referral URL to base your condition on.
5. **Condition**: Specify the nature of your condition by selecting from options like 'Contains', 'Does not contain', 'Is', or 'Is Not'.
6. **Value**: Enter a free text field to define the value that your UTM parameter should match or contrast with.
7. You can also add more conditions by clicking on 'Select’. For each additional condition, you'll need to choose how it relates to the others:
   1. Or: The action will be executed if either of the conditions is met.
   2. And: All conditions must be met for the action to be executed.
8. **Determine the outcome: **After setting your conditions, you'll need to decide what happens when those conditions are met. There are two main actions you can take:
   1. Exclude: This option allows you to ignore certain traffic events from your attribution data, effectively excluding them from analysis.
   2. Label as: This option allows for altering the display name of a record, enabling the renaming of entries such as changing "facebook" to "fb", which results in the display name of the row being updated. When three entries, "fb", "meta", and "facebook", are all labeled as "facebook", the interface consolidates them into a single row, displaying aggregated data for clarity.
   3. Group as : It consolidates multiple entries under a unified category without altering their names. Using the above example, grouping "fb", "meta", and "facebook" under "facebook" creates a single, expandable parent row in the user interface. This row shows aggregated data, with the original three entries detailed underneath.
9. Once you've defined both the conditions and the actions of your rule, review the details to ensure accuracy, add a name to the rule, and proceed to preview the rule. The Preview option lets you see the traffic data affected by the rules, along with a matched/unmatched status. These results can be reviewed before saving the rule.
10. Your new custom rule will now be active, and the attribution logic will adjust accordingly based on the criteria you've set.

> 📘 The attribution status indicator changes to "refreshing" to show that the attribution reports are syncing with the new changes.

***

<br />

## FAQ

### Q: How many custom rules can I have?

A: As many as you like. Keep in mind that we evaluate rules in the order they are sorted. Once the conditions of a rule are met, we execute the action and stop evaluating the rules for that event.

### Q: Are rules case-sensitive?

A: No. We transform both the conditions and the URL to lowercase before checking for any matches.