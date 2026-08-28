---
title: '[4.0][WIP] Model Schema'
excerpt: >-
  Define what goes into a model: the outcome you are explaining, the media you
  think drives it, and the context that explains the rest.
hidden: false
---

# Model Schema

A model schema is a saved answer to the question *what should this model look at*. It names the outcome you want explained, the paid media you believe influences it, the organic and contextual factors that explain the rest, and how those pieces relate to each other.

It is worth being clear about what a schema is not. It is not the model. Training a model is a separate step. A schema is the recipe, and it can be reused, refreshed, and adjusted without starting from nothing each time.

This is also the point where the earlier tabs pay off. A schema can only offer you fields that Data Transformation mapped, and it can only offer you tactics that Data Taxonomy assigned. If something you expect is missing here, the fix is usually one tab upstream.

![The Model Schema tab before any schemas exist](https://files.readme.io/c4329473172a693076af1aa1d6e425d2d82c4034fdb219f46ae7ffbdecf549c2-model-schema-empty.png)

## Creating a schema

Click **Create Data Model** to start. There are four steps.

### Step 1: Model Schema Type

Give the schema a name and choose what it is for.

![Naming a schema and choosing what it should power](https://files.readme.io/4baa47fe72d55cfb3df87a9e139b68b5d9501b9f75147e8c910db97caa331f57-model-schema-type.png)

Name it after the question it answers rather than the method. Revenue MMM UK is more useful in six months than Model 3.

Then choose one or more methods the schema should power:

**Marketing Mix Modelling / Time Testing Experiments** decomposes how much each paid media channel contributed to your KPI, or runs before and after and hold-out tests along a time axis. It needs media spend, revenue data, and a time axis.

**Geo Experiments** compares matched test and control regions to measure incremental lift. It needs test and control regions, a geographic dimension, and revenue.

A schema can serve more than one method, because one well defined variable set can power several. Pick both if you intend to do both.

### Step 2: Variables

This is the substantive step, and it is organised into sections.

![Choosing the KPI, paid media, organic and contextual variables](https://files.readme.io/33f2c89ed584e193201ddafef6667d47ef4101256d3f74172b1757e86048936e-model-schema-variables.png)

**Primary KPI.** The one metric this model exists to explain. Revenue for most commerce businesses, but it could be orders, signups, or installs. Only fields you categorised as KPI in Data Transformation are offered here.

Choose the outcome you are actually trying to grow. If the business is judged on profit, modelling revenue will tell you how to sell more at any margin, which is not the same question.

**Secondary KPIs.** Optional additional outcomes tracked alongside the primary one. Useful when you care about new customer acquisition as well as total revenue.

**Dimensional / hierarchical model.** Turn this on to fit separate coefficients per dimension value, for example per country or per product line, rather than one coefficient for everything. Use it when you genuinely believe media behaves differently across those groups, and when you have enough data in each group to support it. Splitting a thin dataset into ten pieces produces ten unreliable answers rather than one solid one. Only dimensions flagged as measurement dimensions in Data Transformation appear here.

**Paid Media.** Add the channels whose spend you want measured. For each channel you can either take the whole channel, or narrow it to a single tactic within that channel. Tactics come from [Data Taxonomy](https://docs.lifesight.io/docs/4-0-wip-data-taxonomy), which is why classifying campaigns matters before you get here. Once you pick a channel, its spend, impressions and clicks fill in automatically from the mapping you set up in Data Transformation.

Include the media you can plausibly change. Excluding a real channel forces the model to attribute its effect elsewhere, which quietly inflates whatever is left in.

**Organic.** Owned and earned signals such as email sends, organic sessions, or affiliate activity. These matter because they move at the same time as paid media, and leaving them out makes paid media look better than it is.

**Contextual.** Everything else that moves your KPI and has nothing to do with your marketing: seasonality, holidays, promotions, price changes, competitor activity, weather. This is the most commonly skipped section and one of the most valuable. If you ran a 30 percent off promotion in November and do not tell the model, it will credit that revenue to whichever channel happened to be spending.

For organic and contextual variables you also choose how the variable enters the model:

- **Continuous** for a number that varies, such as average discount depth.
- **Binary** for on or off, such as whether a promotion was running.
- **Categorical** for a set of named states, such as promotion type.

### Step 3: Causal Graph

Here you describe how the variables relate. The point is to distinguish between something that causes your KPI to move and something that merely moves at the same time.

The classic trap is a channel that spends more because sales are already rising, rather than sales rising because it spent more. Without the relationships made explicit, a model can read that backwards and recommend more of something that was following demand rather than creating it.

You do not need a perfect diagram. Capture the relationships you are confident about and leave the rest.

### Step 4: Preview

A summary of everything the schema contains before you commit. Read it as a checklist:

- Is the primary KPI the outcome the business is actually judged on?
- Is every meaningful paid channel present?
- Are the big non-marketing drivers of last year's revenue represented in the contextual section?
- If the dimensional option is on, does every group have enough data to stand on its own?

Save when it reads correctly.

## After the schema exists

The schema appears in the Model Schema list, where you can open it to see its composition grouped by category: dimensions first, because they govern how everything below is read, then KPIs, paid marketing, contextual, and organic.

From there a schema can be used to train models, refreshed as new data arrives, and edited when your marketing changes. Adding a new channel next quarter means editing the schema rather than rebuilding from scratch.

## A worked example

A retailer wants to know what drove last year's revenue.

**Type.** Named Revenue MMM, set to Marketing Mix Modelling.

**Primary KPI.** Revenue, from their Shopify data.

**Paid Media.** Google split into Paid Search Brand and Paid Search Non-Brand, because those behave very differently. Meta split into Prospecting and Retargeting. YouTube as a whole channel, since they run only one kind of video campaign.

**Organic.** Email sends, and organic search sessions.

**Contextual.** A binary variable for promotional periods, and a continuous variable for average discount depth. They add these because Black Friday dominates their year and without it the model would hand that revenue to whichever channel was spending in November.

**Causal Graph.** They record that promotions drive revenue directly, and also that promotions drive higher paid social spend, since they scale budgets during sales.

**Preview.** They notice affiliate spend is missing entirely, go back to Integrations to connect it, and return to add it before saving.

That last step is normal. Building a schema is often what reveals the gap in your data.

## Common questions

**A field I need is not in the list.** It has not been mapped, or it has been mapped to the wrong category. Go to [Data Transformation](https://docs.lifesight.io/docs/4-0-wip-data-transformation), find the source, and check the field.

**A tactic I need is not offered.** It has not been created or assigned in [Data Taxonomy](https://docs.lifesight.io/docs/4-0-wip-data-taxonomy).

**How many variables should a model have?**
Fewer than you think. Every variable needs enough data behind it to estimate its effect. With two years of weekly data you have around 100 observations, and thirty variables will overfit. Start with the things you can actually act on.

**Can I have more than one schema?**
Yes, and you often should. A schema for total revenue and a separate one for new customer acquisition answer different questions and deserve different variable sets.

**Do I need to redo this when new data arrives?**
No. The schema keeps reading the sources it was built on. You revisit it when your marketing changes, such as launching a new channel.
