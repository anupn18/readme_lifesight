---
title: ML based Inference
excerpt: Nested Ridge Regression based Robust Incrementality Measurements
deprecated: false
hidden: false
metadata:
  robots: index
---
### The Simple Math Behind It

Let's start with a basic equation:

```text
Sales (or any Outcome) = Baseline (Trends + Brand Equity) Driven + Marketing Driven + Internal Factors Driven + External Factors Driven + Interaction Factors + Noise/Error
```

Where:

* **Baseline**: The expected performance without any marketing efforts - driven by macroeconomic trends, brand loyalty, brand equity or other unknown/omitted variables.
* **Marketing Effects**: The total impact of various paid media marketing activities (Total impact here is the sum of direct & indirect impact from all the marketing activities)
* **Internal Factors**: By other factors primarily managed & controlled by the brand such as social media followers, price changes, promotions, product launches, organic search impressions (SEO)
* **External Factors**: Elements outside of brand's direct control primary driven by competitors and their influence
* **Error**: The unexplained variance (because no model is perfect) - also known as Noise.

***

## Building Up: From Simple Addition to Complex Models

Marketing Mix Modelling evolves from simple linear models to complex, dynamic models that account for diminishing returns, lag effects, and interactions between different variables.

### Step 1: Linear Relationships

Let’s start with a simple linear model. Imagine we have two marketing channels: TV ads and social media campaigns. The equation might look like this:

```plaintext
Sales = Baseline + (TV Spend × TV Effect) + (Social Media Spend × Social Media Effect) + ...
```

Here, each marketing activity's contribution to sales is linear and proportional to the amount spent.

### Step 2: Time Delays and Carryover Effects

Marketing doesn’t always produce immediate results. For example, TV ads might influence people for several weeks, while the effects of a social media campaign could wear off quickly. These lagging effects can be captured using **adstock** and time delay models:

```plaintext
Sales(t) = Baseline + Σ(TV Spend(t-i) × Decay^i × TV Effect) + Σ(Social Media Spend(t-i) × Decay^i × Social Media Effect) + ... 
```

Where:

* `t` is the current time period.
* `i` represents previous time periods (days, weeks, etc.).
* `Decay` is a coefficient that shows how quickly the impact of each marketing activity diminishes over time.

This method allows marketers to understand how long the effects of a campaign last and when the optimal time is to launch a new one.

### Step 3: Diminishing Returns

Marketing's impact on KPI is non linear and complex. We need to transform the input variables, non-linearly, to capture the right impact of these variables on the KPI. It starts with incorporating ad stock / lag effect transformation

However, in reality, spending twice as much on a marketing channel doesn’t always yield twice the results. This phenomenon is known as **diminishing returns**. We can represent this mathematically by adjusting the linear model:

```plaintext
Sales = Baseline + (TV Spend^0.7 × TV Effect) + (Social Media Spend^0.8 × Social Media Effect) + ... 
```

The exponents (0.7 and 0.8) signify the diminishing returns for TV ads and social media, respectively. In practice, this shows that each additional dollar spent is less effective than the previous one.

***

## Challenges of Marketing Mix Modelling

While MMM is a powerful tool, it does come with challenges:

1. **Data Quality**: As with any data-driven approach, the output is only as good as the data input. Poor data quality can skew results.
2. **Multicollinearity**: When marketing channels are highly correlated, it becomes difficult to separate their individual impacts. For example, if TV ads and social media are often used together, it’s hard to isolate the effect of each.
3. **External Factors**: Events like economic downturns, competitor actions, or weather conditions can influence marketing effectiveness but are difficult to account for.
4. **Long-term Effects**: Brand-building activities often have long-term impacts that are difficult to measure using short-term models.
5. **Feature Selection** : We need to include the right set of features/variables in the model to make the right inference. More features will create overfitting problem, Not including the right [confounders/mediators/colliders ](https://docs.lifesight.io/docs/causality-in-mmm) will comprise causal reasoning, adding random variables will introduce noise and cause poor fit

## Conclusion: Where Statistical Rigor Meets Marketing Judgment

Marketing Mix Modelling at Lifesight elevates marketing from intuition-led decisions to evidence-based strategy. But MMM is not a replacement for creativity — it’s a decision intelligence layer that empowers it.

The science lies in the math: structured transformations, causal reasoning, regularisation, and machine-learning-driven inference. The art lies in interpreting these results with brand context, market understanding, and strategic nuance. Together, they reveal not just what is working, but why, how much, and what to do next.

By grounding decisions in a robust measurement framework — and by leveraging the rich KPIs and Causal AI capabilities we support — marketers can confidently optimise budgets, balance short-term efficiency with long-term brand growth, and craft strategies with both precision and creativity.

***

If you’re ready to go deeper into the mechanics, the next step is understanding how regularised ridge regression underpins stable, reliable MMM models. Start [here](https://docs.lifesight.io/update/docs/ridge-regression#/)
