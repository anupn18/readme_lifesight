---
title: Marketing Mix Modelling (COPY)
excerpt: A Comprehensive Guide on Marketing Mix Modelling
deprecated: false
hidden: true
metadata:
  robots: index
---
In today's ever-changing business landscape, making smart marketing decisions isn't just beneficial—it's essential. We all invest heavily in various marketing channels like TV, radio, digital ads, and social media to connect with our audience. But here's the million-dollar question: Which of these channels are driving incremental sales and giving you the best bang for your buck? That's where Marketing Mix Modeling (MMM) comes into play.

For Brands that have access to historical data, MMM is the shortest route to measure incrementality. Lifesight's approach to MMM is causally informed a combination of quasi-causal inference from observational data and causal inference from experiments (which is used for model calibration)

Let's dive into what MMM is all about, why it's a game-changer, and how it can work wonders for your business. 

## The Basics: What is Marketing Mix Modelling?

At its core, Marketing Mix Modelling is a statistical analysis technique used to measure the impact of various marketing activities on sales or other key performance indicators (KPIs). It's like a microscope that allows marketers to zoom in on their efforts and understand which elements are truly driving results. These techniques are time tested and has been in use for decades in the industry.

Imagine you're a chef trying to perfect a recipe. You have various ingredients at your disposal – salt, pepper, herbs, and spices – and you want to know how each one contributes to the final taste. Now, replace `chef` with `marketer`, `recipe` with `marketing strategy`, and `ingredients` with `marketing channels`. This is the essence of Marketing Mix Modelling (MMM). This powerful tool helps marketers dissect and optimize the impact of each channel, ensuring that the perfect combination delivers the most effective results.

At **Lifesight**, we support various KPIs that are essential for businesses to measure performance and optimize campaigns. These include:

* **Revenue**
* **Conversions**
* **Installs**
* **Orders**
* **Store Visits**
* **Registrations**
* **Reach**
* **Subscriptions**
* **Admissions**

These KPIs serve as the dependent variables in our marketing mix models, helping marketers understand the contributions of each channel or activity to the overall business success.

### The Simple Math Behind It

Let's start with a basic equation:

```text
Sales (or any KPI) = Baseline + Marketing Effects + External Factors + Error
```

Where:

* **Baseline**: The expected performance without any marketing efforts.
* **Marketing Effects**: The impact of various marketing activities, like ads, promotions, and social media campaigns.
* **External Factors**: Elements outside of your control, such as the economy, weather, or competitor actions.
* **Error**: The unexplained variance (because no model is perfect).

<br />

## Building Up: From Simple Addition to Complex Models

Marketing Mix Modelling evolves from simple linear models to complex, dynamic models that account for diminishing returns, lag effects, and interactions between different variables.

### Step 1: Linear Relationships

Let’s start with a simple linear model. Imagine we have two marketing channels: TV ads and social media campaigns. The equation might look like this:

```plaintext
Sales = Baseline + (TV Spend × TV Effect) + (Social Media Spend × Social Media Effect)
```

Here, each marketing activity's contribution to sales is linear and proportional to the amount spent.

<br />

### Step 2: Time Delays and Carryover Effects

Marketing doesn’t always produce immediate results. For example, TV ads might influence people for several weeks, while the effects of a social media campaign could wear off quickly. These lagging effects can be captured using **adstock** and time delay models:

```plaintext
Sales(t) = Baseline + Σ(TV Spend(t-i) × Decay^i × TV Effect) + Σ(Social Media Spend(t-i) × Decay^i × Social Media Effect)
```

Where:

* `t` is the current time period.
* `i` represents previous time periods (days, weeks, etc.).
* `Decay` is a coefficient that shows how quickly the impact of each marketing activity diminishes over time.

This method allows marketers to understand how long the effects of a campaign last and when the optimal time is to launch a new one.

<br />

### Step 3: Diminishing Returns

Marketing's impact on KPI is non linear and complex. We need to transform the input variables, non-linearly, to capture the right impact of these variables on the KPI. It starts with incorporating ad stock / lag effect transformation

However, in reality, spending twice as much on a marketing channel doesn’t always yield twice the results. This phenomenon is known as **diminishing returns**. We can represent this mathematically by adjusting the linear model:

```plaintext
Sales = Baseline + (TV Spend^0.7 × TV Effect) + (Social Media Spend^0.8 × Social Media Effect)
```

The exponents (0.7 and 0.8) signify the diminishing returns for TV ads and social media, respectively. In practice, this shows that each additional dollar spent is less effective than the previous one.

<br />

## Challenges of Marketing Mix Modelling

While MMM is a powerful tool, it does come with challenges:

1. **Data Quality**: As with any data-driven approach, the output is only as good as the data input. Poor data quality can skew results.
2. **Multicollinearity**: When marketing channels are highly correlated, it becomes difficult to separate their individual impacts. For example, if TV ads and social media are often used together, it’s hard to isolate the effect of each.
3. **External Factors**: Events like economic downturns, competitor actions, or weather conditions can influence marketing effectiveness but are difficult to account for.
4. **Long-term Effects**: Brand-building activities often have long-term impacts that are difficult to measure using short-term models.
5. **Feature Selection** : We need to include the right set of features/variables in the model to make the right inference. More features will create overfitting problem, Not including the right [confounders/mediators/colliders ](https://docs.lifesight.io/docs/causality-in-mmm) will comprise causal reasoning, adding random variables will introduce noise and cause poor fit

<br />

## Conclusion: The Art and Science of Marketing

Marketing Mix Modelling at Lifesight transforms marketing from a purely creative endeavor into a data-driven science. But like the chef at the beginning of our analogy, the art lies in interpreting the results and crafting the perfect mix. MMM isn’t about replacing creativity with numbers but rather informing creativity with insights.

By understanding the principles behind MMM and leveraging the various KPIs we support, marketers can make more informed decisions, optimize their marketing spend, and ultimately, deliver a strategy that’s as balanced and effective as a master chef’s signature dish.