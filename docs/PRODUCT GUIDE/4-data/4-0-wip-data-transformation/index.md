---
title: '[4.0][WIP] Data Transformation'
excerpt: >-
  Turn the raw columns your sources produce into the shared set of Lifesight
  fields that every model and report reads from.
hidden: true
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

### Dimensions and metrics

Every column is sorted into one of two roles. The distinction is not cosmetic. It decides what the platform is allowed to do with the column.

**A dimension describes a row.** Country, Campaign Name, Device, Objective, Date. Dimensions are what you group by, filter by and split by. You never add them up. Adding two country names together is meaningless, which is exactly why they are kept separate from metrics.

**A metric measures a row.** Spend, Clicks, Impressions, Attributed Revenue. Metrics are numbers that can be combined, and every metric carries a **roll-up** that says how.

The roll-up matters more than it looks. When Lifesight collapses 30 daily rows into one monthly number, the roll-up decides the answer:

- **Sum** for anything that accumulates, such as spend, clicks and impressions
- **Average** for a rate or a ratio
- **Min**, **Max** or **Count** for the less common cases

Summing a percentage is the classic error. Thirty daily click-through rates added together produce a number that means nothing, so a rate must average rather than sum.

If a column is in the wrong group, open its actions menu and use **Make Dimension** or **Make Metric**. That reclassification is a display and modelling decision only. It does not alter the underlying data.

### Data types

Each field also has a data type, which says what shape its values take. For standard Lifesight fields the type is fixed by the field itself, so you rarely set it by hand. You will see it on custom fields and when checking that a column arrived correctly.

| Type | What it holds |
| --- | --- |
| **Text** | Any string. The default for names and labels. |
| **Integer** | A whole number, such as clicks or impressions. |
| **Decimal** | A number with a fractional part. |
| **Number** | A precise decimal, used where exactness matters. |
| **Big Number** | A number too large for the standard numeric range. |
| **Currency** | A monetary amount. |
| **Percentage** | A rate, stored so it reads as a percentage. |
| **Boolean** | True or false. Useful for flags such as whether a promotion ran. |
| **Date** | A calendar date, formatted `YYYY-MM-DD`. |
| **Date and time** | A date with a time, formatted `YYYY-MM-DD HH:MM:SS`. |
| **JSON** | Structured data kept as-is. |

The two date formats are worth remembering, because ambiguous dates are the most common import problem. `03/04/2025` could be March or April depending on who wrote it, while `2025-04-03` cannot be misread.

### Measurement dimensions

Some dimensions are just descriptive. Others are ones you actively want to measure along, and those need to be marked.

A **measurement dimension** is a dimension you have flagged as something models and taxonomy should be able to work with. Turn it on for the dimensions you want to measure by, using the toggle in the dimension's row.

Flagging one has two specific effects:

- It appears under **Your dimensions** when you build a data model, which is what makes it available for a dimensional or hierarchical model that fits separate coefficients per country, per brand or per product line
- It carries through to **Data Taxonomy**, where it becomes available as a column and as a field you can write rules against

Be selective. Country, brand, region and product line are usually worth flagging because you genuinely want to model or classify along them. Ad ID is not, because nobody models per ad, and flagging everything makes the model builder and the rules editor harder to use for no benefit.

To change a field, open the actions menu at the end of its row and choose **Edit**.

## Mapping a source

Before you get to individual columns, a source has to describe itself as a whole. That is what the left rail of a source's page is for. It summarises the row contract, which is the shape of one row of this data:

- **Data category**, which decides which Lifesight fields are offered for its columns
- **Date**, the date column and its granularity, taken from how the integration was set up
- **Channel**, how this data maps to a channel Lifesight recognises

The Channel entry is the one you may need to set, and it matters because everything downstream groups by channel rather than by whichever name the upload happened to have. A file called `Q4_partner_export.csv` means nothing to a model. Knowing that its spend is Paid Social does.

Native connectors already know their channel, so Google Ads arrives carrying Google and YouTube without you doing anything. Uploaded files do not, so this is mainly a step for CSV and spreadsheet sources.

Opening it asks how the data is shaped, and there are three possibilities. Picking the right one is the whole task.

| Shape | What it looks like | What you do |
| --- | --- | --- |
| **One channel per column** | Columns are the channels: `DATE, EMAIL_SPEND, OBA_SPEND, INKPACT_SPEND` | Assign a channel to each column |
| **A column holds the channel** | One column names the channel per row: `date, channel, spend` with values `fb`, `google` | Pick that column, then map each raw value to a channel |
| **The whole file is one channel** | No channel column, because every row is the same thing | Confirm the single channel for the source |

For the second shape, Lifesight suggests matches for common abbreviations, so `fb` proposes Facebook Ads and `bing` proposes Microsoft Ads. Check the suggestions rather than accepting them blindly, because in-house shorthand is rarely as obvious as it looks to the person who invented it.

Getting this right once means every column underneath is already attributed to the correct channel, which is why it comes before column mapping.

## The two ways a field gets its value

When you edit a field, the section called **How this field gets its value** offers two choices. Which one you want depends on whether the answer varies from row to row.

| Use case | Choose | Read more |
| --- | --- | --- |
| The source reports the value, and it changes row to row | **A field from this source** | [Map a field from a source](https://docs.lifesight.io/docs/4-0-wip-map-field-from-source) |
| The value is the same on every row from this source | **A fixed value for every row** | [Set a fixed value for a source](https://docs.lifesight.io/docs/4-0-wip-fixed-value-source) |

And before either of those, the source itself needs a channel: [Map a source to a channel](https://docs.lifesight.io/docs/4-0-wip-map-source-channel).

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