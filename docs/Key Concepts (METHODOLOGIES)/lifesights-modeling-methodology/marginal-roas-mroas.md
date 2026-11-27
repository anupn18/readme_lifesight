---
title: Marginal ROAS (mROAS)
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
At Lifesight, we are committed to helping businesses maximize the effectiveness of their marketing investments. One of the key metrics that we use to optimize marketing campaigns is **mROAS** (Marginal Return on Ad Spend). Unlike traditional ROAS, which measures the overall return on all ad spend, **mROAS** specifically quantifies the return on **the next dollar spent**, allowing businesses to make more granular and optimized decisions about budget allocation.

This document explains **mROAS**, how it is calculated for every channel, the two marginal columns you see on a model's Contribution tab (**miROAS** and **mcROAS**), and how they help in making informed, data-driven decisions for budget allocation.

***

## What is mROAS?

**Marginal ROAS (mROAS)** measures the incremental **KPI** generated from the **next unit** of ad spend. It is the **slope** of the response curve at a given spend level, and it helps marketers decide where to allocate additional resources most efficiently.

### Key Formula:

```plaintext
mROAS = (Marginal KPI) / (Marginal Spend)
```

* **Marginal KPI**: The increase in the relevant KPI (e.g., revenue, conversions, installs) that comes from the next dollar (or any currency unit) spent on a particular channel.
* **Marginal Spend**: The incremental increase in the spend for that channel.

> 📘 mROAS helps answer the question: **"For the next dollar I spend, which channel will provide the highest KPI growth?"**

***

## Why Use mROAS?

While traditional ROAS gives an overall view of how efficiently a campaign is driving a KPI, **mROAS** allows marketers to drill down and optimize their budget by focusing on **marginal efficiency**. Here's why mROAS is critical in the context of marketing mix optimization:

1. **Optimization of Budget Allocation**:
   * Traditional ROAS focuses on the past performance of the entire campaign, but mROAS provides a **forward-looking view**. By using mROAS, Lifesight helps businesses allocate future budgets to channels that offer the best return for the next dollar spent in terms of relevant KPIs like **revenue**, **conversions**, **installs**, or **store visits**.
2. **Diminishing Returns & Saturation**:
   * Channels tend to experience **diminishing returns** after a certain point. With mROAS, you can understand when additional spending on a channel will yield diminishing KPI returns, enabling smarter decisions around increasing or decreasing ad spend on specific channels.
3. **Precise Decision-Making**:
   * mROAS allows for **fine-tuned adjustments** to your marketing mix. Instead of scaling back or increasing ad spend on entire channels based on past performance, mROAS shows you the **marginal effect** of small adjustments, ensuring more precise decision-making.

***

## How is mROAS Calculated at Lifesight?

The calculation of mROAS at Lifesight is grounded in **marketing mix models (MMM)**. Each paid channel in the model has a response curve built from two transformations. mROAS is read off that curve.

### 1. **Adstock Transformation** (Lagged Effects)

The response to marketing spend is not always immediate. For each channel, we apply the **adstock transformation** to account for **carryover effects**. The adstock transformation ensures that the effect of previous campaigns is accounted for when calculating the **current marginal KPI**. In other words, we include the impact of past spend that still influences current KPI growth.

#### Formula:

```plaintext
Adstocked Spend (today) = Spend (today) + Decay Rate × Adstocked Spend (yesterday)
```

This ensures that the mROAS calculation takes into account both **current and past spending effects** on the channel, resulting in a more accurate marginal KPI.

### 2. **Saturation Transformation** (Diminishing Returns)

For each media channel, the relationship between spend and KPIs is **non-linear**. This means that after a certain point, increasing spend yields progressively smaller KPI improvements. To account for this, Lifesight uses the **Hill saturation transformation**, which models the **diminishing returns** in each channel.

#### Formula:

```plaintext
Saturation = Adstocked Spend^alpha / (Adstocked Spend^alpha + Half Saturation Point^alpha)
```

* **alpha** controls the shape of the curve (how quickly returns start to fall).
* **Half Saturation Point** is the spend level at which the channel reaches half of its maximum response.

This transformation ensures that as spend increases, the **marginal KPI** (and so mROAS) decreases, reflecting the reality of diminishing returns.

### 3. **Marginal KPI and Marginal Spend**

Once the **Adstock** and **Saturation transformations** are applied, we calculate the **marginal KPI** and **marginal spend** for each channel. This is done by adding one more unit of spend to the channel's current spend level and measuring the additional KPI the response curve predicts.

#### Steps:

1. **Current Spend Level**: Take the channel's average spend per model period (per day for a daily model, per week for a weekly model) over the selected analysis period.
2. **Baseline KPI**: Read the KPI the response curve predicts at that spend level.
3. **Incremental Spend**: Add one unit of spend (one dollar, or one unit of the model's currency).
4. **Marginal KPI**: Read the additional KPI the curve predicts for that extra unit.

Finally, the **mROAS** for that channel is calculated as:

```plaintext
Current KPI = KPI the response curve predicts at the current spend level
Next KPI    = KPI the response curve predicts after adding one unit of spend
mROAS       = Next KPI - Current KPI
```

Because the extra spend is exactly one unit, the difference between the two KPI values is the marginal KPI per unit of spend.

This process is repeated for all channels. On the Contribution tab, this value is shown as **miROAS**.

***

## miROAS and mcROAS on the Contribution Tab

A model's Contribution tab shows two marginal columns for every paid channel. They answer two different questions.

| Column | Question it answers |
| :-- | :-- |
| **miROAS** | "What does the **next dollar** on this channel return, at today's spend level?" |
| **mcROAS** | "If I spend **one more average day** on this channel, what does the channel's **overall ROAS** become?" |

For models whose KPI is conversions (or any non-revenue KPI), the same two columns are shown as **miCPA** and **mcCPA**.

Both columns are calculated over the **period you select** for the saturation curves on the Contribution tab: the last 1, 2, 3, 6, 9 or 12 months of the model's data. The default is the last 12 months. miROAS and mcROAS for a given period always come from the same period, so the two columns can be compared directly.

### miROAS

**miROAS** is the mROAS described in the section above: the incremental revenue from the **next dollar** of spend at the channel's current spend level.

* The current spend level is the channel's average spend per model period over the selected period.
* The value is read from the channel's response curve, so it includes carryover (adstock) and diminishing returns (saturation).
* A channel that is close to saturation has a low miROAS, even if its overall ROAS is high.

#### Formula:

```plaintext
Current Revenue = incremental revenue the response curve predicts at the current spend level
Next Revenue    = incremental revenue the response curve predicts after adding one dollar of spend
miROAS          = Next Revenue - Current Revenue
```

For example, if the curve predicts $10,000.00 of incremental revenue at the current spend level and $10,001.50 after one more dollar, miROAS is 1.50.

### mcROAS

**mcROAS** shows how the channel's **overall** ROAS changes if you add a small amount of extra spend. It combines the channel's current incremental revenue with the extra revenue that miROAS predicts for the added spend.

The added spend is **one average day of spend** for the channel in the selected period.

#### Inputs (all for the selected period):

* **Spend**: the channel's average monthly spend.
* **Incremental Revenue**: the channel's average monthly incremental revenue from the model.
* **miROAS**: the marginal ROAS at the current spend level (from the section above).
* **Delta**: one average day of spend = Spend / 30.

#### Steps:

1. **Extra incremental revenue from the added spend**:

```plaintext
Extra Revenue = miROAS × Delta
```

2. **Incremental revenue after the added spend**:

```plaintext
Adjusted Revenue = Incremental Revenue + Extra Revenue
```

3. **ROAS after the added spend**:

```plaintext
mcROAS = Adjusted Revenue / (Spend + Delta)
```

> 📘 **How to read mcROAS:** "Over the selected period, if we add one more average day of spend on this channel, we expect **Extra Revenue** more incremental revenue. At that higher spend, the channel's overall ROAS becomes **mcROAS**."

mcROAS sits **between** the channel's average ROAS and its miROAS:

* If miROAS is **lower** than the average ROAS, the channel is saturating. mcROAS is slightly **below** the average ROAS, because the extra spend returns less than the spend before it.
* If miROAS is **higher** than the average ROAS, the channel still has room to grow. mcROAS is slightly **above** the average ROAS.

#### Example:

| Input | Value |
| :-- | :-- |
| Average monthly spend | $30,000 |
| Average monthly incremental revenue | $90,000 (average ROAS = 3.00) |
| miROAS | 1.50 |
| Delta (one average day of spend) | $30,000 / 30 = $1,000 |

1. Extra Revenue = 1.50 × $1,000 = $1,500
2. Adjusted Revenue = $90,000 + $1,500 = $91,500
3. mcROAS = $91,500 / ($30,000 + $1,000) = **2.95**

The channel returns $3.00 per dollar on average, but the next dollar returns only $1.50. Adding one more day of spend brings the overall ROAS down from 3.00 to 2.95.

### miCPA and mcCPA (non-revenue KPIs)

For models whose KPI is conversions, installs, store visits or another count, Lifesight shows cost per acquisition instead of ROAS.

* **miCPA** is the cost of the **next** conversion at the current spend level:

```plaintext
Current Conversions = incremental conversions the response curve predicts at the current spend level
Next Conversions    = incremental conversions the response curve predicts after adding one dollar of spend
miCPA               = 1 / (Next Conversions - Current Conversions)
```

* **mcCPA** follows the same steps as mcROAS, with incremental conversions in place of incremental revenue:

```plaintext
Marginal Conversions per Dollar = Next Conversions - Current Conversions
Extra Conversions               = Marginal Conversions per Dollar × Delta
Adjusted Conversions            = Incremental Conversions + Extra Conversions
mcCPA                           = (Spend + Delta) / Adjusted Conversions
```

For CPA, **lower is better**. A miCPA that is higher than the channel's average CPA means the next conversion costs more than the average one, so the channel is saturating.

### When the columns show "-"

* **miROAS / miCPA** shows "-" when the model has no response curve for the channel. miCPA also shows "-" when the marginal conversions per dollar is zero or negative, because a cost per conversion cannot be calculated.
* **mcROAS / mcCPA** shows "-" when the channel has no spend or no incremental revenue (or conversions) in the selected period.

> 🚧 **Short periods:** With the last 1 month selected, the average monthly spend is that single month, so miROAS and mcROAS can move a lot with seasonality and one-off campaigns. Use 1 to 3 months to see recent behaviour, and 6 to 12 months for budget decisions.

***

## Visualizing mROAS and Saturation Curves

At Lifesight, we visualize **saturation curves** for each media channel to show how spend impacts KPIs. These curves help marketers understand where they are experiencing **diminishing returns** and where there may still be room for additional investment.

### Key Points on Saturation Curves:

* **Carryover**: This point on the curve reflects the impact of past campaigns (the "carryover effect"). Even without current spend, the channel will still generate some KPI growth due to the lingering effects of past investments.

* **Initial Spend**: The current level of spend and its associated KPI is plotted to give a benchmark for comparison. miROAS is the slope of the curve at this point.

* **Optimized Spend**: Based on mROAS, we can calculate the **optimal spend point**, where the channel generates the highest KPI return per incremental dollar spent.

These curves show when it makes sense to **increase**, **decrease**, or **maintain** spending on a particular channel.

***

## Budget Allocation Based on mROAS

The goal of mROAS is to ensure that marketing budgets are **optimally allocated** across channels. By using mROAS to guide decisions, businesses can shift spend to the channels that will generate the highest incremental KPI returns, thereby maximizing overall campaign performance.

### Steps to Optimize Budget Allocation:

1. **Evaluate Current Spend**: Start with the current allocation of spend across channels.
2. **Calculate mROAS for Each Channel**: Using the methodology described above, calculate the mROAS (miROAS) for each channel.
3. **Reallocate Budget Based on mROAS**: Shift the budget from channels with lower mROAS to those with higher mROAS, so that every incremental dollar goes where it returns the most.
4. **Monitor Saturation**: Continuously monitor the saturation curves to ensure that additional spend doesn’t push a channel into diminishing returns.

### Example of Budget Reallocation:

* **Channel A** has an mROAS of 2.0, meaning every additional dollar spent yields $2 in revenue.
* **Channel B** has an mROAS of 4.0, meaning every additional dollar spent yields $4 in revenue.

In this case, it would make sense to **shift budget from Channel A to Channel B** until the mROAS converges and the marginal returns between the two channels are balanced.

***

## The Convergence of mROAS

As we continue to optimize the allocation of marketing budgets, the **mROAS across channels tends to converge**. This is known as the **equilibrium state**, where each channel is generating roughly the same marginal KPI return. At this point, additional reallocation will not significantly improve overall performance, and the budget is said to be optimally distributed.

### Key Points:

* **Equilibrium State**: When mROAS for all channels reaches a similar value, indicating that the budget is distributed in the most efficient way possible.
* **Continuous Monitoring**: While achieving equilibrium is ideal, ongoing monitoring is essential to account for changes in external factors (e.g., seasonality, market conditions) and maintain optimal budget allocation.

***

## Conclusion

**mROAS** is a powerful tool for optimizing marketing spend at a granular level, ensuring that every incremental dollar is working to maximize KPI returns. On the Contribution tab, **miROAS** shows the return on the next dollar at today's spend, and **mcROAS** shows what the channel's overall ROAS becomes after one more average day of spend. By focusing on the **marginal efficiency** of ad spend and incorporating **adstock** and **saturation transformations**, Lifesight's methodology enables businesses to make data-driven decisions that lead to higher efficiency and greater overall campaign performance.

For further information on **adstock transformation**, **saturation curves**, or budget optimization techniques, refer to the related methodology articles available in the Lifesight documentation.
