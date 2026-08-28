---
title: '[4.0][WIP] Data Transformation'
excerpt: >-
  Turn the raw columns your sources produce into the shared set of Lifesight
  fields that every model and report reads from.
hidden: false
---
Every platform names things its own way. Google Ads gives you a column called `spend`. Meta gives you one called `spend` too, but its `attributed_revenue` counts conversions on a different window. A spreadsheet from your finance team might call the same idea `Media Investment`. None of that matters to the people running campaigns, and it matters enormously to a model, which needs one definition of spend rather than four.

Data Transformation is where you settle that. For each column arriving from each source, you say what it means in Lifesight terms. Once you have, everything downstream speaks one vocabulary.

## Two words worth learning first

**A source column** is what the platform gives you. It has whatever name the platform chose and holds whatever the platform put in it. You do not control this.

**A Lifesight field** is the shared name that Lifesight and your models use. Spend, Impressions, Clicks, Revenue, Date, Country. You do control this, and it is the same everywhere.

The whole tab is about drawing a line between the two.

## The sources list

Opening the tab shows one row per connected source.

![The Data Transformation tab listing connected sources](https://files.readme.io/7c659f1e1038ea3858de314b27a9f2f76e9f03d5d5b5fd44239c983d9c8a81b9-transformation-sources.png)

| Column | What it means |
| --- | --- |
| **Integration Name** | The source. A green tick means its mandatory fields are mapped and it is ready to be used. |
| **Channel(s)** | The channels this source feeds. Google Ads, for example, carries both Google and YouTube. |
| **Category** | The data category the source belongs to. This decides which Lifesight fields are offered when you map its columns. |
| **Granularity** | How finely the data is reported over time. Daily for most ad platforms. |
| **Last Modified On** and **Last Modified By** | Who last changed the mapping, and when. Useful when a number moves and nobody knows why. |

Click **View Fields** on a row to open that source's fields.

## Data categories

Every source belongs to a category, and the category decides which Lifesight fields make sense for its columns. This is why you are not offered Impressions when mapping a column from an accounting export.

| Category | What belongs here |
| --- | --- |
| **KPIs** | The outcomes you care about: revenue, conversions, orders, installs. |
| **Paid Marketing** | Spend, impressions, clicks and the rest, grouped by ad platform. |
| **Organic** | Owned and earned signals such as email sends or organic sessions. |
| **Contextual** | Things that explain the world around your marketing: seasonality, holidays, promotions, weather. |
| **Others** | Anything not yet categorised. |

## The field workshop

Inside a source, its columns are sorted into two groups, because models treat them very differently.

![The field workshop, showing dimensions and metrics for a source](https://files.readme.io/d4ea54dc44db99082dcb5d85ac086c19f5ee6bbeaf0c9da06759ea6c748c4858-transformation-field-workshop.png)

**Dimensions** are the things you slice by. Country, Campaign Name, Device, Objective. They describe a row rather than measure it. You never add dimensions up.

**Metrics** are the numbers. Spend, Clicks, Impressions, Attributed Revenue. Every metric has a **roll-up**, which is how it collapses when rows are combined. Spend sums. A rate would average. Getting the roll-up right matters, because summing a percentage produces nonsense.

Each row shows the **Input Field** (the source column) next to the **Lifesight Field** it maps to, along with its data type. Fields marked CUSTOMIZABLE are mapped for you but you are allowed to change them. Native platform connectors arrive with most of this already done, so in practice your job is to check the important fields rather than map everything from scratch.

To change a field, open the actions menu at the end of its row and choose **Edit**.

## The two ways a field gets its value

When you edit a field, the section called **How this field gets its value** offers two choices. Which one you want depends on whether the answer varies from row to row.

| Use case | Choose | Read more |
| --- | --- | --- |
| The source reports the value, and it changes row to row | **A field from this source** | [Map a field from a source](https://docs.lifesight.io/docs/4-0-wip-map-field-from-source) |
| The value is the same on every row from this source | **A fixed value for every row** | [Set a fixed value for a source](https://docs.lifesight.io/docs/4-0-wip-fixed-value-source) |

The test is simple. If the answer would be identical on every single row of this source, it is a fixed value. If it varies, it needs to come from a column, even a messy one.

## The rest of the field editor

Below the value section you will find:

**Where it lands.** The data category this field files under, inherited from the source.

**Metric type.** For paid marketing sources, which of the standard measures this is. Spend is mandatory for a source you intend to model.

**Roll-up and format.** How the number folds over a date range, and how many decimal places it keeps.

Click **Save changes** when you are done.

## Common questions

**Do I have to map everything?**
No. Map what you will use. Ignoring a column is reversible.

**What is mandatory?**
For a paid marketing source you intend to model, Spend and a date field. Until they are mapped the source shows as Unmapped and downstream tools cannot use it.

**I changed a mapping. Does it apply to old data?**
Yes. A mapping is a definition rather than a one time import, so corrected mappings apply to the history you already hold.

**Where do I set what a campaign is for?**
Not here. Classifying campaigns into tactics is [Data Taxonomy](https://docs.lifesight.io/docs/4-0-wip-data-taxonomy). This tab is about what columns mean, not how campaigns are grouped.
