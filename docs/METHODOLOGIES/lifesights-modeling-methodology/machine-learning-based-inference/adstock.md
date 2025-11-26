---
title: Transformations - Adstock
excerpt: Understanding adstock (decay and lag effects) in Marketing Mix Modeling
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Why we need to Transform ?

Transformations in Marketing Mix Modeling takes 2 forms :

1. Adstock Tranformations
2. Saturation Transformations (Discussed <Anchor label="here" target="_blank" href="https://docs.lifesight.io/update/docs/marginal-roas-mroas#/">here</Anchor> )

These transformations help us incorporate the non-linear nature of relationships - namely decay/lag in the effect and diminishing returns - between marketing variables and the outcome and also help us incorporate real world patterns of how marketing actually drive results into the model.

At Lifesight we treat these transformations as "weakly informative priors" and the range of these distributions are informed by domain knowledge

In this section, we dive deep into Adstock transformation

***

## What is Adstock Transformation?

Adstock Transformation is a fundamental concept in marketing analytics that models the **carryover effects** of advertising over time. It captures the idea that advertising effects don’t happen instantly and then vanish; rather, they build up and decay over time, influencing consumer behaviour long after the ad has been shown.

For example, when someone sees an ad on TV today, they might not make a purchase immediately. However, the ad’s message stays in their memory, and they may take action later. Adstock helps us quantify this **"memory effect"**, modelling how the impact of an ad lingers and decays over time.

### Why is Adstock Important?

Understanding adstock is crucial because it helps measure the **true impact** of your advertising campaigns. Without adstock, marketing models would only capture the immediate effects of ads, ignoring the longer-term influence. By accounting for adstock, you can:

* **Measure long-term ROI**: Capture delayed consumer responses.
* **Optimize media planning**: Understand how long the effects of your ads last.
* **Improve budget allocation**: Invest more effectively in ads that have lasting impacts.

In marketing analytics, especially in **Marketing Mix Modeling (MMM)**, adstock is used to measure both the **short-term** and **long-term** effects of advertising across different media channels.

### How Adstock Works

The core principle of adstock is that the effect of advertising decays over time. This means that each period’s advertising impact is a combination of the current period’s ad spend and a portion of the previous period’s effect that carries over.

### The Adstock Formula

The basic formula for adstock is:

```
Adstock(t) = Advertising(t) + DecayRate * Adstock(t-1)
```

Where:

* **Adstock(t)** is the total advertising effect in period `t`.
* **Advertising(t)** is the ad spend in period `t`.
* **DecayRate** is a value between 0 and 1, representing the fraction of the previous period’s ad effect that carries over.

### Example:

Let’s say you spend $1000 on advertising in Week 1, and the **decay rate** is 0.7 (70% of the effect carries over to the next week). In this case:

* **Week 1**: $1000 (full effect from Week 1).
* **Week 2**: $700 (70% of Week 1’s effect carries over).

This approach allows you to measure not just the immediate effects of advertising but also the residual impact on future periods.

### Types of Adstock Transformations

There are **two primary types** of adstock transformations that we support:

1. **Geometric Adstock**
2. **Weibull PDF (Probability Density Function) Adstock**

Each of these transformations offers different ways to model how the effects of advertising decay over time, depending on the nature of the ad campaign and the media channel.

_Note : Lifesight uses adstock-ed modeling to understand the short-term impact of advertising. This short term impact is then converted to Immediate & Carryover. For long term impact we perform [Mediation Analysis.](https://docs.lifesight.io/update/docs/advanced-modeling-scenarios#/)_

### 1. Geometric Adstock

**Geometric Adstock** is the simplest and most widely used form of adstock transformation. It assumes that the advertising effect decays at a **constant rate** over time. This approach is ideal for media channels where the impact of ads fades predictably, such as **digital ads** or **social media campaigns**.

#### How Geometric Adstock Works:

Geometric adstock uses a **fixed decay rate** to model how the effect of an ad diminishes over time. Each period’s advertising effect is a combination of the current period’s ad spend and a constant percentage of the previous period’s effect.

#### Formula:

```
Adstock(t) = Advertising(t) + DecayRate * Adstock(t-1)
```

Where **DecayRate** is a constant value between 0 and 1. A higher decay rate (e.g., 0.8) means the ad effect carries over longer, while a lower decay rate (e.g., 0.3) means the effect fades more quickly.

#### Example:

If you spend $1000 on ads in Week 1 and the decay rate is 0.5 (50% of the ad effect carries over to the next week):

* **Week 1**: $1000 (full ad effect).
* **Week 2**: $500 (50% of Week 1’s effect).
* **Week 3**: $250 (50% of Week 2’s effect), and so on.

#### Key Characteristics:

* **Simplicity**: Only requires one parameter—the decay rate—making it easy to implement.
* **Constant Decay**: Assumes that the ad effect decays at the same rate each period, which is suitable for channels where ads have short-term impacts.

#### Best Use Cases:

* **Digital media**: Search ads, display ads, or social media campaigns where consumers respond quickly.
* **Frequent, short-term campaigns**: Works well when the goal is to drive immediate consumer action.
* <br />

### 2. Weibull PDF Adstock (Probability Density Function)

The **Weibull PDF Adstock** model introduces more flexibility compared to geometric adstock. It allows for a **lagging effect**, meaning that the impact of an ad may **increase** after some time before it starts to decay. This is useful for high-consideration products (e.g., cars or appliances) where consumers may not act immediately after seeing an ad.

#### How Weibull PDF Adstock Works:

Weibull PDF uses two parameters—**shape** and **scale**—to model ad decay. The **shape** parameter controls whether the ad effect peaks after a delay, while the **scale** parameter controls how quickly the ad effect decays after it peaks.

#### Formula:

```
Adstock(t) = Advertising(t) + WeibullPDF(t)
```

Where:

* **Shape**: Determines whether the ad effect decays immediately or peaks after a delay.
* **Scale**: Determines the rate at which the ad effect decays after peaking.

#### Example:

Consider a TV ad for a high-value product. The shape parameter allows for a delayed peak in consumer response:

* **Week 1**: The ad is shown, but immediate consumer response is low.
* **Weeks 2-3**: The effect peaks as consumers begin considering the product.
* **Weeks 4 onwards**: The ad effect gradually decays as fewer consumers recall the ad.

#### Key Characteristics:

* **Lagged Effect**: Allows the ad effect to increase after a delay, which is ideal for high-value or high-consideration products.
* **Flexible Decay**: Offers more control over how the ad effect decays, making it suitable for offline media.

#### Best Use Cases:

* **High-consideration products**: Cars, appliances, or services where consumers take time before making a decision.
* **Offline media**: TV, radio, or print campaigns where immediate consumer action is not expected.

***

### Choosing the Right Adstock Model

The choice of adstock model depends on the nature of your advertising campaign and the media channel you're using:

* **Geometric Adstock**: Best for **digital channels** (search, display, social media) where the consumer response is quick and predictable.
* **Weibull PDF Adstock**: Best for **high-consideration purchases** (cars, electronics) or **offline media** (TV, radio) where consumer action might be delayed.

***

## Conclusion

Adstock transformation is a powerful tool for modeling the **long-term impact of advertising**. Whether you're running short-term digital campaigns or long-term brand-building initiatives, understanding how adstock works helps you optimize your advertising strategy, improve ROI, and make informed media decisions.

By supporting **Geometric** and **Weibull PDF** transformations, you can tailor your adstock model to fit the specific needs of your campaign and media mix, ensuring that you capture the full value of your advertising investment.

***

Next let us look into [Saturation modeling](https://docs.lifesight.io/update/docs/marginal-roas-mroas#/)
