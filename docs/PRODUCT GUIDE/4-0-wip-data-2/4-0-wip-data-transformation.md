---
title: '[4.0][WIP] Data Transformation'
excerpt: >-
  Turn the raw columns your sources produce into the shared set of Lifesight
  fields that every model and report reads from.
hidden: false
---

# Data Transformation

Every platform names things its own way. Google Ads gives you a column called `spend`. Meta gives you one called `spend` too, but its `attributed_revenue` counts conversions on a different window. A spreadsheet from your finance team might call the same idea `Media Investment`. None of that matters to the people running campaigns, but it matters enormously to a model, which needs one definition of spend, not four.

Data Transformation is where you settle that. For each column arriving from each source, you say what it means in Lifesight terms. Once you have, everything downstream speaks one vocabulary.

## Two words worth learning first

**A source column** is what the platform gives you. It has whatever name the platform chose, and it holds whatever the platform put in it. You do not control this.

**A Lifesight field** is the shared name that Lifesight and your models use. Spend, Impressions, Clicks, Revenue, Date, Country. You do control this, and it is the same everywhere.

The whole tab is about drawing a line between the two.

## The sources list

Opening the tab shows one row per connected source.

![The Data Transformation tab listing connected sources](./images/transformation-sources.png)

| Column | What it means |
| --- | --- |
| **Integration Name** | The source. A green tick means its mandatory fields are mapped and it is ready to be used. |
| **Channel(s)** | The channels this source feeds. Google Ads, for example, carries both Google and YouTube. |
| **Category** | The data category the source belongs to, such as Paid Marketing. This decides which Lifesight fields are offered when you map its columns. |
| **Granularity** | How finely the data is reported over time. Daily for most ad platforms. |
| **Last Modified On** and **Last Modified By** | Who last changed the mapping, and when. Useful when a number moves and nobody knows why. |

Click **View Fields** on a row to open that source's fields.

## Data categories

Every source belongs to a category, and the category decides which Lifesight fields make sense for its columns. This is why you are not offered Impressions when mapping a column from your accounting export.

| Category | What belongs here |
| --- | --- |
| **KPIs** | The outcomes you care about: revenue, conversions, orders, installs. |
| **Paid Marketing** | Spend, impressions, clicks and the rest, grouped by ad platform. |
| **Organic** | Owned and earned signals such as email sends or organic sessions. |
| **Contextual** | Things that explain the world around your marketing: seasonality, holidays, promotions, weather. |
| **Others** | Anything not yet categorised. |

## The field workshop

Inside a source, its columns are sorted into two groups, because models treat them very differently.

![The field workshop, showing dimensions and metrics for a source](./images/transformation-field-workshop.png)

**Dimensions** are the things you slice by. Country, Campaign Name, Device, Objective. They describe a row rather than measure it. You never add dimensions up.

**Metrics** are the numbers. Spend, Clicks, Impressions, Attributed Revenue. Every metric has a **roll-up**, which is how it collapses when rows are combined. Spend sums. A rate would average. Getting the roll-up right matters, because summing a percentage produces nonsense.

Each row shows the **Input Field** (the source column) next to the **Lifesight Field** it maps to, along with its data type. Fields marked CUSTOMIZABLE are mapped for you but you are allowed to change them. Native platform connectors arrive with most of this already done, so in practice your job is to check the important fields rather than map everything from scratch.

To change a field, open the actions menu at the end of its row and choose **Edit**.

## Where a field's value comes from

This is the heart of the tab. When you edit a field, the section called **How this field gets its value** offers two choices.

![Editing a metric, with the value coming from a field in the source](./images/transformation-field-from-source.png)

### A field from this source

The value is read from a column in this source, row by row. This is the normal case and the one you will use most.

You pick the source column on the left under **FROM**, and the Lifesight field it becomes on the right under **TO**. The data type sits next to the Lifesight field. For standard Lifesight fields the type is fixed by the field itself, because Spend is always a number and Date is always a date. Choosing the target is choosing the type.

Underneath, a preview panel shows real sample values from your data running through the mapping, so you can see what will actually be stored before you save. If the values cannot satisfy the field you picked, for example text where a number is expected, the panel says so plainly rather than letting you find out later.

**Use this when** the source genuinely reports the thing you want, which is almost always true for spend, impressions, clicks, revenue and dates coming from an ad platform.

### A fixed value for every row

The value is the same for every row from this source. Nothing is read from a column.

![Editing a metric, with a fixed value applied to every row](./images/transformation-fixed-value.png)

You type the value on the left under **Fixed value**, and choose the Lifesight field it fills on the right. Every row that arrives from this source gets that value.

**Use this when** the information is true of the source as a whole but is not present in the data. Some real examples:

- A CSV of offline retail sales has no country column because it is all United Kingdom. Set Country to a fixed value of `United Kingdom`.
- A spreadsheet tracking a single sponsorship deal has no channel column. Set Channel to a fixed value of `Sponsorship`.
- A partner sends you a monthly file covering one brand only, and your models split by brand. Set Brand to a fixed value.

The test is simple. If the answer would be the same on every single row of this source, a fixed value is right. If it varies row to row, it needs to come from a column, even if that column is messy.

## The rest of the field editor

Below the value section you will find:

**Where it lands.** The data category this field files under. It is inherited from the source, so a Google Ads field lands in Paid Marketing.

**Metric type.** For paid marketing sources, which of the standard measures this is. Spend is mandatory for a source you intend to model, and impressions, clicks and revenue complete the picture.

**Roll-up and format.** How the number folds over a date range, and how many decimal places it keeps.

When you are done, click **Save changes**. Cancel discards everything on the screen.

## A worked example

A retailer connects Google Ads and opens its fields.

`spend` is already mapped to Spend with a roll-up of Sum. They leave it alone.

`attributed_revenue` is mapped to Attributed Revenue. They check the preview, see values like `379.28` flowing through unchanged, and confirm this is the revenue figure they want the model to explain rather than a different conversion window.

`country` is mapped and switched on as a measurement dimension, because they want the option of modelling per country later.

They then upload a CSV of in-store sales. It has `date`, `store`, and `sales`, and no country column at all, because every store is in the United Kingdom. They map `sales` to Revenue as a field from the source, and they add Country as a fixed value of `United Kingdom`. Now the in-store data and the online data can sit side by side in the same model without one of them having a hole where country should be.

## Common questions

**Do I have to map everything?**
No. Map what you will use. Columns you ignore stay available if you change your mind, and ignoring a column is reversible.

**What is mandatory?**
For a paid marketing source you intend to model, Spend and a date field are the minimum. Until they are mapped the source shows as Unmapped and downstream tools cannot use it.

**I changed a mapping. Does it apply to old data?**
Yes. A mapping is a definition rather than a one time import, so corrected mappings apply to the history you already hold as well as to new data.

**Two sources report the same thing. Do I map both?**
Yes, both to the same Lifesight field. That is exactly the point. When Google's `spend` and Meta's `spend` both map to Spend, a model can compare them.

**Can one source column feed two different Lifesight fields?**
Not from a single mapping row. Map it once to the first field, save, then create a second custom field pointed at the same column for the other use.

**Where do I set what a campaign is for?**
Not here. Classifying campaigns into tactics is [Data Taxonomy](https://docs.lifesight.io/docs/4-0-wip-data-taxonomy). This tab is about what columns mean, not about how campaigns are grouped.
