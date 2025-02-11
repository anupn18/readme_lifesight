---
title: 'Split Testing : Treatment / Control Assignment'
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
# Random Assignment and Stratified Random Assignment in Experiments

<br />

When running experiments, particularly in marketing campaigns, it's essential to divide your audience into two distinct groups: the **Treatment** group, which receives the intervention (e.g., a marketing campaign), and the **Control** group, which does not. This split allows us to assess the true impact of the intervention by comparing the results of these two groups.

There are different ways to assign users to these groups. In this document, we will cover two commonly used methodologies: **Random Assignment** and **Stratified Random Assignment**. Each has its advantages depending on the goals of the experiment and the characteristics of the audience.

***

## Random Assignment

### What is Random Assignment?

**Random Assignment** is the most straightforward way to allocate an audience between Treatment and Control groups. In this method, users are randomly divided into these groups based on the predefined percentage split. The randomness ensures that differences between the two groups are due to the experimental intervention rather than pre-existing characteristics.

### How Random Assignment Works ?

1. **Audience Definition**: Define the size of the audience.
2. **Assign Split Percentages**: Choose the percentage of users for the Treatment and Control groups (e.g., 70% Treatment, 30% Control).
3. **Random Assignment Process**: Users are assigned to groups based on a random process that adheres to the specified percentage.

### Example : 

Assume you have an audience of 100 users and wish to assign 70% to the Treatment group and 30% to the Control group. Each user is randomly assigned to one of the groups according to the defined split.

<br />

## Stratified Random Assignment

### What is Stratified Random Assignment?

**Stratified Random Assignment** takes random assignment one step further by ensuring that key characteristics (such as age, gender, or location) are evenly distributed between the Treatment and Control groups. This method is especially useful when you want to control for specific factors that might influence the experiment's outcome.

### How Stratified Random Assignment Works ?

1. **Identify Key Variables**: Determine which characteristics (e.g., age, income, location) should be balanced between the groups.
2. **Divide into Strata**: Split the audience into subgroups (strata) based on these characteristics. For example, you might create strata for different age ranges.
3. **Random Assignment Within Each Stratum**: Within each stratum, users are randomly assigned to the Treatment or Control group in a way that maintains the balance of the key variables.

### Example :

Suppose your audience consists of 100 users, divided into three age groups:

- **Age Group 1** (18-25 years): 30 users
- **Age Group 2** (26-40 years): 40 users
- **Age Group 3** (41+ years): 30 users

You want a 50/50 split between Treatment and Control groups for each age group.

<br />

## Comparison: Random Assignment vs Stratified Random Assignment

| **Feature**           | **Random Assignment**                                                                                                        | **Stratified Random Assignment**                                                                                                            |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **Definition**        | Randomly assigns users to Treatment or Control groups without considering their characteristics (e.g., age, gender, income). | Assigns users to Treatment or Control groups based on specific characteristics (e.g., age, income) to ensure balance across segments.       |
| **Use Case**          | Used when there are no specific characteristics to control for, and simple random distribution is sufficient.                | Used when balancing certain characteristics between groups is critical for fairness (e.g., age, income).                                    |
| **Group Composition** | Groups may have different distributions of characteristics, which can lead to imbalances.                                    | Groups are balanced based on predefined characteristics, ensuring both groups are comparable.                                               |
| **Fairness**          | Fair but may result in uneven distribution of key characteristics (e.g., one group could have more younger users).           | Fair and ensures even distribution of key characteristics across Treatment and Control groups.                                              |
| **Bias Control**      | Reduces bias by randomizing, but may not account for imbalances in characteristics like age, gender, or income.              | Reduces bias by ensuring specific characteristics are evenly distributed, providing better control over imbalances.                         |
| **Complexity**        | Simple to implement, as it only requires randomization without considering group segmentation.                               | More complex, as it requires stratifying the audience by characteristics before random assignment.                                          |
| **Example**           | Users are randomly assigned to either Treatment or Control, regardless of age or other characteristics.                      | Users are first divided into age groups (e.g., 18-25, 26-40), and then randomly assigned within those groups to Treatment or Control.       |
| **When to Use**       | When you don't need to account for specific characteristics and just want random distribution of users.                      | When you need to ensure balance across important characteristics (e.g., ensuring the age or income distribution is similar in both groups). |
| **Risk of Imbalance** | Higher risk of uneven distribution in terms of specific characteristics, which can affect the results of the experiment.     | Low risk of imbalance, as groups are carefully balanced across key characteristics before assignment.                                       |
| **Statistical Power** | Can lead to reduced statistical power if important characteristics are not balanced between groups.                          | Maintains or improves statistical power by ensuring important characteristics are balanced across groups.                                   |

<br />

> 📘 **Note:**
> 
> - At Lifesight, we offer both **Random Assignment** and **Stratified Random Assignment** methodologies.
> - By default, Random Assignment is applied. However, if you have specific variables that need to be balanced (e.g., age), we can enable Stratified Random Assignment to ensure these characteristics are evenly distributed across groups.