---
title: '[4.0][WIP] Data'
excerpt: >-
  Bring all your marketing and business data into Lifesight, integrate your
  sources and shape it into the inputs your models run on.
hidden: true
---
Every number Lifesight shows you starts somewhere else: a row in Google Ads, a line in a Shopify order, a column in someone's spreadsheet. The Data module brings all of it together, maps it to one set of definitions, and keeps it current, so your team works from one set of numbers instead of stitching them together by hand.

It is the foundation of the platform, and it connects to a wide range of sources and destinations. Centralizing your marketing, business, and customer data removes silos, improves accuracy, and gives your team one current view to work from.

Nothing downstream can be better than the data underneath it. A media mix model that reports the wrong revenue is not a modeling problem. It is a data problem, and it gets solved here.

This guide walks you through connecting your sources, managing consent, and getting your data ready to use.

> This module was previously called **Data OS**. It is now simply **Data**. The capabilities have not been removed, only renamed and reorganised.

## How does data works in Lifesight

Data is organised into four sections, each handling one stage of the work in sequence.

| Where                   | What it does                           | The question it answers                                                   |
| ----------------------- | -------------------------------------- | ------------------------------------------------------------------------- |
| **Integrations**        | Brings the data in                     | Where does our data come from, and is it arriving?                        |
| **Data Transformation** | Puts every source in the same language | Does "revenue" here mean the same thing as "revenue" there?               |
| **Data Taxonomy**       | Groups it the way the business thinks  | Which campaigns belong to which tactic (prospecting, retargeting, brand)? |
| **Model Schema**        | Prepares it for a model                | Which fields go into a given model, and how?                              |

You will find these as four tabs across the top of the Data page, in the order you work through them.

![The Data module, showing the Integrations tab with two connected sources](https://files.readme.io/85c8e00f5f9ed1abf12c7963ef0224fd16faec6133a89a8c12812f9e1fe4e39c-integrations-list.png)

## Why the work is split this way

It is tempting to think of data setup as one big task. Splitting it into four keeps each decision in the place where it belongs, and it means you rarely have to redo work.

**Integrations** is about access and plumbing. You are answering a yes or no question: is Lifesight allowed to read this account, and is the data flowing. Once a source is connected and healthy, you mostly stop thinking about it.

**Data Transformation** is about meaning. Google calls a column `cost`. Meta calls it `spend`. Your spreadsheet calls it `Media Investment`. All three are the same idea, and a model needs them to be the same field. This tab is where you say so, once, and every source that lands afterwards inherits the same vocabulary.

**Data Taxonomy** is about grouping. Two campaigns can both be Google Ads spend and still be doing completely different jobs, one defending your brand terms and one prospecting for new customers. Averaging them together hides the thing you most want to know. This tab is where you sort campaigns into tactics that reflect how you actually run marketing.

**Model Schema** is about a specific question. You do not model everything at once. You pick an outcome, pick the media that plausibly drives it, add the context that explains the rest, and leave out the noise. This tab is where you define that selection and save it so it can be reused and refreshed.

## The order to work in

The tabs after Integrations stay locked until you have at least one active integration. That is deliberate. There is nothing to map, group, or model until data is arriving. If you hover a locked tab it will tell you the same thing.

A sensible first pass looks like this.

1. **Connect one source you know well.** Your largest ad platform is usually the right choice, because you will spot a wrong number immediately. See [Integrations](https://docs.lifesight.io/docs/4-0-wip-integrations) for the connection flow, and the per platform pages for anything specific to that source.
2. **Wait for the first sync.** The initial pull covers your history, so it takes longer than later refreshes. The integration shows as Healthy when it is done.
3. **Open Data Transformation and check the fields.** Most columns from a native platform are mapped for you. Your job is to confirm the important ones (spend, revenue, the date column) landed on the right Lifesight fields, and to fix anything that did not.
4. **Connect the rest of your sources.** Now that you know what good looks like, the remaining platforms go faster.
5. **Open Data Taxonomy and assign tactics.** Start with the campaigns carrying the most spend. You do not have to classify everything on day one.
6. **Build a Model Schema when you have a question to answer.** Not before.

Steps 1 to 4 are usually one sitting. Steps 5 and 6 benefit from a conversation with whoever runs the campaigns, because they involve judgement about how your marketing is actually organised.

## What each tab gives you

### Integrations

The catalogue of sources Lifesight can read, the wizard that connects them, and the health view that tells you whether they are still working. Sources fall into three groups: native platform connectors that authenticate with a sign in or an API key, files and spreadsheets you upload or link, and data warehouses you point at your own tables.

### Data Transformation

A list of your connected sources, and behind each one, the columns it produces. For every column you decide two things: which Lifesight field it becomes, and where its value comes from. A field can take its value from a column in that source, or it can be a fixed value stamped on every row from that source. Those two options cover the large majority of real setups.

### Data Taxonomy

A table of your campaigns with the spend behind each one, and a tactic column you fill in. You can assign tactics by hand for a handful of campaigns, or write rules that assign them automatically based on the campaign name or any other dimension. Rules are the sane choice at scale, because new campaigns get classified the moment they appear.

### Model Schema

A guided flow that captures what a model is made of: the outcome you are explaining, the paid media you think drives it, the organic and contextual variables that explain the rest, and the causal relationships between them. Save it once and it becomes a reusable definition rather than a one off setup.

## A worked example

A retailer selling truck and car accessories wants to know how much of last year's revenue their paid media actually caused.

They connect **Google Ads** and **Meta Ads**, selecting the five ad accounts that carry their spend. Both go Healthy after the first sync.

In **Data Transformation** they open Google Ads and look at the fields. `spend`, `clicks`, and `impressions` are already mapped. `attributed_revenue` is mapped to Attributed Revenue, which is what they want. They notice their Meta account reports currency in USD while a small regional account reports in CAD, so they leave that one out for now rather than mixing currencies.

In **Data Taxonomy** they see 300 campaigns. Rather than clicking through all of them, they write three rules: campaign names containing `Brand` become Paid Search Brand, names containing `NB` become Paid Search Non-Brand, and everything on Meta with `Prospecting` in the name becomes Paid Social Prospecting. That classifies most of their spend in a few minutes. The long tail gets assigned by hand later.

In **Model Schema** they create a schema called Revenue MMM, set the primary KPI to Revenue, add Google and Meta as paid media channels split by tactic, and add a contextual variable for promotional periods. That schema is what their media mix model runs on.

## Common questions

**Do I have to finish one tab before starting the next?**
For the first source, yes, roughly. After that the tabs stop being sequential. Connecting a new integration later sends you back to Data Transformation to check its fields, but you are not starting over.

**What happens if I map something wrong?**
You change it and save. Mappings are definitions, not one way imports. Corrected mappings apply going forward and to the historical data already held.

**Who on my team should own this?**
Integrations usually sits with whoever has admin access to the ad accounts. Data Transformation and Model Schema suit an analyst. Data Taxonomy works best when the person who names the campaigns is in the room, because they know what the naming conventions were meant to mean.

**Something is not arriving. Where do I look first?**
The Integrations tab shows a status against every source. Start there, then read the troubleshooting section on the relevant platform page.
